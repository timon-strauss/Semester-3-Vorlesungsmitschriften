
bsp: 10 Lebensmittelläden; Verkaufsfläche X (in 1000 qm); Jahresumsatz (in Mio €)

| i | $x_i$ | $y_i$ | $x_i - \bar{x}$ | $y_i - \bar{y}$ |  $(x_i - \bar{x})^2$ |  $(y_i - \bar{y})^2$ | $(x_i - \bar{x}) · (y_i - \bar{y})$|
|-|-|-|-|-|-|-|-|
|1 | 0,5 | 3,0 | -0,54 | -2,64 | 0,2916 | 6,9696 | 1,4256 |
|2 | 0,9 | 5,1 | -0,14 | -0,54 | 0,0196 | 0,2916 | 0,0756 |
|3 | 1,1 | 5,5 | 0,06  | -0,14 | 0,0036 | 0,0196 | -0,0084 |
|2 | 1,5 | 7,3 | ... |
|5 | 1,2 | 6,2 |
|6 | 1,4 | 7,0 |
|7 | 1,6 | 8,1 |
|8 | 0,8 | 4,9 |
|9 | 1,0 | 6,1 |
|10 | 0,4 | 3,1 | | | | | ... |
|$\sum$ | 10,4 | 5,64 | 0 | 0 | 1,464 | 24,964 | 5,934 |

$$p = \frac{5,934}{\sqrt{1,464 · 24,964}} = 0,982$$

=> Sehr starker positiver linearer Zusammenhang

Regression bilden:

$$B_1 = \frac{5,934}{1,464} = 4,053 $$
$$B_0 = 5,64 - 4,053 = 1,425$$

$$Jahresumsatz = 1,425 + 4,053 · f_i$$


Qualität der Regression => Determinationskoeffizient:

$$R^2 = \frac{4,053^2 · 1,464}{24,964} = 0,963 = 96,3 \%$$

=> 96,3% der Streuung von $y_i$ wird linear durch $x_i$ erklärt

Falls $R^2$ gegen null geht besteht kein **linearer** zusammenhang.
Achtung: kann trotzdem einen zusammenhang haben muss aber nicht