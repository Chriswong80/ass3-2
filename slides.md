---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<!-- __AUDIO_INTRO_DO_NOT_TOUCH__ -->

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### ANOVA of Part Resistance by Pressure (Machine 1)

We perform an ANOVA to assess if varying pressure has a statistically significant effect on the part resistance for Machine 1. The Upper Specification Limit (USL) for Part Resistance is 10.

**ANOVA Results Interpretation:**
Please refer to the output of the previous R cell for the full ANOVA summary, including the p-value for the 'Pressure_Factor' term.
*   If the p-value for 'Pressure_Factor' is less than your chosen significance level (e.g., 0.05), it indicates a statistically significant effect of pressure on part resistance.
*   The boxplot provides a visual representation of the distribution of part resistance at different pressure settings, with the dashed orange line indicating the USL.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/anova_part_resistance_by_pressure_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

----

:::: {.columns}
::: {.column width="50%"}
### ANOVA of Part Resistance by Temperature (Machine 1)

We perform an ANOVA to assess if varying temperature has a statistically significant effect on the part resistance for Machine 1. The Upper Specification Limit (USL) for Part Resistance is 10, and there is no Lower Specification Limit (LSL).

**ANOVA Results Interpretation:**
Please refer to the output of the previous R cell for the full ANOVA summary, including the p-value for the 'Temperature_Factor' term.
*   If the p-value for 'Temperature_Factor' is less than your chosen significance level (e.g., 0.05), it indicates a statistically significant effect of temperature on part resistance.
*   The boxplot provides a visual representation of the distribution of part resistance at different temperature settings, with the dashed orange line indicating the USL.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/anova_part_resistance_by_temperature_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::
