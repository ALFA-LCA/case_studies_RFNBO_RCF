# H2: Time averaging

-   How to average over different timeframes

![](../images/h2_grid.svg)

Electrolyser running at 27.8 MW (100 GJ/h) with fully renewable, directly connected electricity, complemented by grid electricity. Oxygen is vented.

This case study shows that until 2030, it is possible to choose between monthly averaging or hourly averaging. As an example, we show an example of both. We pick one hour with particularly low renewables to exemplify how the calculation has to be done.

## Assumptions

| Parameter                   |    Symbol          | Monthly averaging                | Hourly averaging, low renewables |
|----------------------------|--------------|:----------------:|:---------------:|
| Efficiency of the electrolyser | $\eta_{ely}$        | $60\color{grey}{\%}$                         {: colspan=2} |
| Relevant renewable electricity used | $el_{ren}$     | $60\ \color{grey}{TJ}$                     | $40\ \color{grey}{GJ}$     |
| Relevant grid electricity used | $el_{grid\_ely}$ | $12\ \color{grey}{TJ}$                      | $60\ \color{grey}{GJ}$     |
| Grid electricity for auxiliaries | $el_{grid\_aux}$ | $3.6\ \color{grey}{TJ}$                     | $5\ \color{grey}{GJ}$     |
| Fully renewable electricity GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ {: colspan=2} |
| Grid GHG intensity | $CI_{grid}$                  | $50\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$  {: colspan=2} |

## Calculation

### Hourly averaging, low renewables

Amount of hydrogen produced: 

$$
{prod}_{H2} = \left(el_{ren} + {el}_{grid\_ely} \right)  \times  \eta_{ely} \approx 60\ \color{grey}{GJ}
$$

Total GHG intensity:

$$
\begin{aligned}
{E}_{H_2} &= (e_{i,elastic} + e_{i,rigid} - e_{ex-use}) + e_p + e_{td} + e_u - e_{ccs}
\\
e_{i,rigid},\ e_{ex-use},\ e_{td},\ e_u,\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic} &= \frac{{el}_{grid\_ely}  \times  CI_{grid}}{{prod}_{H2}} &\approx 50\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_p &= \frac{el_{grid\_aux} \times  CI_{grid}}{{prod}_{H2}} &\approx 4.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
{E}_{H2} &&\approx 54.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\end{aligned}
$$

??? failure "Threshold not reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is not met. We cannot declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output: $Share_{RFNBO-H_2} = 0\color{grey}{\%}$ because threshold is not met. The whole fuel output cannot be declared as RFNBO or low-carbon fuel.

??? tip "Hour with high renewables"
    This example should not imply that hourly averaging is bad. In other hours, the share of renewables is higher than the average, and a higher share of the production can be declared as RFNBO. In many cases, monthly averaging might not reach the threshold, and the whole monthly production could not be declared as RFNBO.

### Monthly averaging

Amount of hydrogen produced:

$$
{prod}_{H2} = \left(el_{ren} + {el}_{grid\_ely} \right)  \times  \eta_{ely} \approx 43.2\ \color{grey}{TJ}
$$

Total GHG intensity:

$$
{E}_{H2} = \frac{\left( {el}_{grid\_ ely} + el_{grid\_aux} \right)  \times  CI_{grid}}{{prod}_{H2}} \approx 18.1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
$$

??? success "Threshold reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output: 

$$
Share_{RFNBO-H_2} = \frac{el_{ren}}{el_{ren} + {el}_{grid\_ely}} \approx 83\color{grey}{\%}
$$

The remainder is low-carbon fuel.

## Conclusion

This case study shows how averaging over shorter time scales can exclude some periods with low renewables from the RFNBO production. In other cases that are not shown here, the contrary could happen that the average over a longer period has a too high GHG intensity to qualify.

