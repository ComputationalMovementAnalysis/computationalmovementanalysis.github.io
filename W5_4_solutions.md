
## Solutions




Hover over the code and copy the content by clicking on the clipboard icon on the top right. You can now paste this into an R-Script.



```r

# task 1 ########################################################################

crop_fanel <- read_sf("00_Rawdata/Feldaufnahmen_Fanel.gpkg")

head(crop_fanel)

summary(crop_fanel)

unique(crop_fanel$Frucht)

st_crs(crop_fanel)

ggplot(crop_fanel) +
  geom_sf(aes(fill = Frucht))


# task 2 ########################################################################


wildschwein_summer <- wildschwein_BE %>%
  filter(month(DatetimeUTC) %in% 5:6)
  
wildschwein_summer <-  st_join(wildschwein_summer, crop_fanel)

wildschwein_summer

ggplot(crop_fanel) +
  geom_sf(aes(fill = Frucht)) +
  geom_sf(data = wildschwein_summer)









# task 3 ########################################################################


library(forcats)

wildschwein_smry <- wildschwein_summer %>%
  st_set_geometry(NULL) %>%
  mutate(
    hour = hour(round_date(DatetimeUTC,"hour")),
    Frucht = ifelse(is.na(Frucht),"other",Frucht),
    Frucht = fct_lump(Frucht, 5,other_level = "other"),
  ) %>%
  group_by(TierName ,hour,Frucht) %>%
  count() %>%
  ungroup() %>%
  group_by(TierName , hour) %>%
  mutate(perc = n / sum(n)) %>%
  ungroup() %>%
  mutate(
    Frucht = fct_reorder(Frucht, n,sum, desc = TRUE)
  )


p1 <- ggplot(wildschwein_smry, aes(hour,perc, fill = Frucht)) +
  geom_col(width = 1) +
  scale_y_continuous(name = "Percentage", labels = scales::percent_format()) +
  scale_x_continuous(name = "Time (rounded to the nearest hour)") +
  facet_wrap(~TierName ) +
  theme_light() +
  labs(title = "Percentages of samples in a given crop per hour",subtitle = "Only showing the most common categories")

p1

p1 +
  coord_polar()  +
  labs(caption = "Same visualization as above, displayed in a polar plot")


# task 4 ########################################################################

veg_height <- rast("00_Rawdata/vegetationshoehe_LFI.tif")


tm_shape(veg_height) + 
  tm_raster(palette = "viridis",style = "cont", legend.is.portrait = FALSE) +
  tm_layout(legend.outside = TRUE,legend.outside.position = "bottom", frame = FALSE)




# task 5 ########################################################################

veg_height_df <- terra::extract(veg_height,st_coordinates(wildschwein_BE))


wildschwein_BE <- cbind(wildschwein_BE,veg_height_df)

wildschwein_BE

```

