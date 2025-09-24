# H1: Co-products

-   How to allocate emissions to oxygen

-   How to calculate the share of RFNBO with emissions from auxiliaries

![](../images/h1_allocation.svg)

Fully renewable electricity is attributed zero GHG emissions. Therefore, the only emissions come from auxiliaries.

??? info "Auxiliaries"
    Auxiliary inputs are all inputs not contributing to the heating value of the RFNBO. In the case of water electrolysis, this might be water supply and treatment, heat and other similar input.

    To simplify the example, we grouped all of them together and displayed the impact directly related to the energy in the RFNBO output.

Emissions can be allocated to the co-products by the economic value (according to point 15(f), because oxygen has no energy content).

## Assumptions

The main assumption is that the oxygen is valorized (sold) as a product. For electrolysers where the oxygen has no economic value, no emissions can be allocated to it.

We assume that auxiliaries are run on grid electricity. It would of course be possible to use renewable electricity for them too.

| Parameter                   |    Symbol          | Example value           |
|----------------------------|:--------------:|:------------------------:|
| Efficiency of the electrolyser | $\eta_{ely}$ | $60\color{grey}{\%}$ |
| Grid electricity for auxiliaries | $el_{grid\_aux}$ | $0.05\ \color{grey}{\left.MJ_{el}\middle/MJ_{hydrogen}\right.}$       |
| Economic value of RFNBO hydrogen | $v_{hydrogen}$  | $6\ \color{grey}{\left.\unicode{x20AC}\middle/{kg}_{hydrogen}\right.}$   |
| Economic value of oxygen | $v_{oxygen}$ | $0.3\ \color{grey}{\left.\unicode{x20AC}\middle/{kg}_{oxygen}\right.}$  |
| Ratio (mass) of produced oxygen per of hydrogen | $r_{oh}$ | $4\ \color{grey}{\left.{kg}_{oxygen}\middle/{kg}_{hydrogen}\right.}$ |
| Fully renewable electricity GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
| Grid GHG intensity | $CI_{grid}$                  | $50\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$  |

## Calculation

Emissions attributed to all products: 

$$
\begin{aligned}
{E}_{products} &= \left(e_{i,elastic} + e_{i,rigid} - e_{ex-use}\right) + e_p + e_{td} + e_u - e_{ccs}
\\
e_{i,rigid},\ e_{ex-use},\ e_{td},\ e_u,\ e_{ccs} &&= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_{i,elastic} &= CI_{ren} \times \eta_{ely} &= 0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
e_p &= {CI}_{grid} \times el_{grid\_aux} &= 2.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\\
E_{products} &&=  2.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
\end{aligned}
$$

Emissions attributed to hydrogen:

$$
E_{hydrogen} = E_{products} \times \frac{v_{hydrogen}}{v_{hydrogen} + v_{oxygen} \times r_{oh}} = 2.1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}
$$

??? success "Threshold reached"
    The threshold of $28.2\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{hydrogen}\right.}$ is met. We can declare the fuel as RFNBO (or low carbon fuel).

Share of RFNBO in the output: $Share_{RFNBO-H_2} = 100\color{grey}{\%}$

## Conclusion

This case study shows that the share of RFNBO is calculated on the energy share of relevant inputs, while emissions are calculated based on all emissions, including auxiliaries. The emissions can be attributed to co-products, in case of products without energy content, economic allocation is used.

