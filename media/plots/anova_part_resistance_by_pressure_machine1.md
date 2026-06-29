# R Code for ANOVA and Boxplot of Part Resistance by Pressure (Machine 1)
library(tidyverse)
library(plotly)

# Filter data for Machine 1
machine1_data_p <- X037 %>% filter(Machine == 1)

# Convert Pressure to a factor
machine1_data_p$Pressure_Factor <- as.factor(machine1_data_p$Pressure)

# Perform ANOVA for the effect of Pressure
anova_result_p <- aov(PartResistance ~ Pressure_Factor, data = machine1_data_p)
cat("ANOVA Summary for Part Resistance by Pressure (Machine 1):\n")
print(summary(anova_result_p))

# Generate boxplot
p_p <- machine1_data_p %>% 
  ggplot(aes(x = Pressure_Factor, y = PartResistance, fill = Pressure_Factor)) +
  geom_boxplot(outlier.colour = "red", outlier.shape = 8, outlier.size = 2) +
  geom_hline(yintercept = 10, linetype = "dashed", color = "#D55E00", linewidth = 1) + # USL
  labs(
    title = "Boxplot of Part Resistance by Pressure (Machine 1)",
    x = "Pressure",
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

plotly_plot_p <- ggplotly(p_p)
saveWidget(plotly_plot_p, file = "media/plots/anova_part_resistance_by_pressure_machine1.html", selfcontained = TRUE)
