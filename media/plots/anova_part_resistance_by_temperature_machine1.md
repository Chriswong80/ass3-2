# R Code for ANOVA and Boxplot of Part Resistance by Temperature (Machine 1)
library(tidyverse)
library(plotly)
library(htmlwidgets)

# Filter data for Machine 1
machine1_data_t <- X037 %>% filter(Machine == 1)

# Convert Temperature to a factor
machine1_data_t$Temperature_Factor <- as.factor(machine1_data_t$Temperature)

# Perform ANOVA for the effect of Temperature
anova_result_t <- aov(PartResistance ~ Temperature_Factor, data = machine1_data_t)
cat("ANOVA Summary for Part Resistance by Temperature (Machine 1):\n")
print(summary(anova_result_t))

# Generate boxplot
p_t <- machine1_data_t %>% 
  ggplot(aes(x = Temperature_Factor, y = PartResistance, fill = Temperature_Factor)) +
  geom_boxplot(outlier.colour = "red", outlier.shape = 8, outlier.size = 2) +
  geom_hline(yintercept = 10, linetype = "dashed", color = "#D55E00", linewidth = 1) + # USL
  labs(
    title = "Boxplot of Part Resistance by Temperature (Machine 1)",
    x = "Temperature",
    y = "Part Resistance"
  ) +
  scale_fill_manual(values = c("#0072B2", "#D55E00", "#009E73")) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, face = "bold"),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = "white", color = NA),
    plot.background = element_rect(fill = "white", color = NA),
    legend.position = "none"
  )

plotly_plot_t <- ggplotly(p_t)
saveWidget(plotly_plot_t, file = "media/plots/anova_part_resistance_by_temperature_machine1.html", selfcontained = TRUE)
