### Abstract
We simulated the Herlaut diagram (H-R diagram) through statistical plotting and conducted multinomial logistic regression using R to develop a model for star recognition and classificatio

## Background
A star is a massive self-luminous celestial body of gas that shines by radiation derived from its internal energy sources. The data set we want to explore collected luminosity, temperature, radius, magnitude, color, spectral class, and star type of 240 different stars.

## Getting the Dataset
Access data from Kaggle: 

[Star Dataset on Kaggle](https://www.kaggle.com/datasets/deepu1109/star-dataset)


## Data Description

1. Luminosity (L)
   
The quantitative variable L describes luminosity of the target star in Watt, which is the total amount of electromagnetic energy emitted per unit of time by a star. In our dataset, it ranges from 3.062e+22 Watt to 3.252e+32 Watt.

2. Temperature (K)
   
K describes the surface temperatures of stars in Kelvin. It ranges from 1939 K to 40000 K.

3. Radius (R/R0)
   
Radius ranges from 0.0084 to 1948.5 and is measured in ratio: radius of stars expressed relative to that of the Sun. The Sun has a zero point radius which equals 6.95x10ˆ8 meter.

4. Absolute magnitude
   
Absolute magnitude measures the brightness of a star from a distance of 10 parsecs away in Mv, where a parsec is equal to 3.26 light-years.

5. Color & Spectral class
    
Color contains 9 different types: Red, Orange-Red, Orange, Pale-yellow-orange, Yellow, Yellow-White, White, Blue-White, and Blue. Spectral class contains 7 types: O(hottest), B, A, F, G, K, and M(coolest). O stars include bluish white stars, with surface temperature of 25000 - 50000 K. M stars are red, at only
about 3000 K.

6. Star type
    
We have 6 star types: Red Dwarf, Brown Dwarf, White Dwarf, Main Sequence , SuperGiant, and HyperGiant. Each type contains 40 observations.

## 

## Conclusion
The H–R diagram (Hertzsprung–Russell diagram) is a scatter plot of stars showing the relationship between the stars’ absolute magnitudes versus their effective temperatures.

![H-R Diagram](H-R%20Diagram.jpg)


We fit multinomial logistic regression models by using forward selection, backward elimination, and stepwise selection(both). Backward elimination and stepwise selection both have AIC = 30.22474 and they reach the same model, while forward selection have an AIC = 180. Thus we pick the model with a lowest AIC value.

### Coefficients:

|              | (Intercept) | A_M       | R        |
|--------------|-------------|-----------|----------|
| **Red**      | -208.99504  | 18.728238 | 6.914394 |
| **Brown**    | -106.19504  | 12.058530 | 7.909280 |
| **White**    | -70.33756   | 10.385723 | -244.689645 |
| **Super**    | -417.22644  | -70.021861 | 7.311421 |
| **Hyper**    | -79.76816   | 7.189164  | 7.915531 |

We use confusion matrix and get an accuracy of 1.

## Tools
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/r/r-original.svg" title="R" alt="R" width="40" height="40"/>&nbsp;
 
</div>
