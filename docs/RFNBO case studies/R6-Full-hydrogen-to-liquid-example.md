# R6: Full hydrogen to liquid example

-   How to combine the previous examples and where to find additional information.

![](../images/r6-optimized.svg)

For the hydrogen production, refer to [hydrogene example](#h3-hydrogen-full-example)

??? "CO~2~ source"
    ## CO~2~ source
    
    ### Eligibility for the e~ex\ use~ “credit”
    
    -   The carbon incorporated into the fuel can be counted as negative emissions if it would have otherwise been emitted as CO~2~ to the atmosphere and stems from air capture, biofuel, RCF or RFNBO production or combustion or an already emitting geological source. Until 2035, also fossil CO~2~ is eligible if taken into account in an effective carbon pricing system. [GHG.10](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q36](../FAQ/faq.md#Q36) [Q37](../FAQ/faq.md#Q37) [Q38](../FAQ/faq.md#Q38) [Q39](../FAQ/faq.md#Q39) [Q40](../FAQ/faq.md#Q40) [Q41](../FAQ/faq.md#Q41) [Q43](../FAQ/faq.md#Q43) [Q42](../FAQ/faq.md#Q42) [Q43](../FAQ/faq.md#Q43) [Q44](../FAQ/faq.md#Q44) [Q-Annex3](https://energy.ec.europa.eu/document/download/21fb4725-7b32-4264-9f36-96cd54cff148_en?filename=2024%2003%2014%20Document%20on%20Certification.pdf)
    
    ### Example in this case study
    
    The CO~2~ comes from a biomass boiler.
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Emissions from CO~2~ capture and supply | $CI_{CO2}$ | $3.6\ \color{grey}{\left.g\,CO_2\,eq\middle/kg\ CO_{2}\right.}$ |
        
    
    
??? "Methanol production"
    ## Methanol production
    
    ### Example in this case study
    
    The inputs are supplied by the processes described above, the auxiliaries use grid electricity. We assume no additional non-biogenic GHG emissions in the process.
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Input of hydrogen | $meoh_{H2}$ | $1.2\ \color{grey}{\left.MJ_{H2}\middle/MJ_{MeOH}\right.}$ |
    |GHG intensity of hydrogen | ${CI}_{H2}$| $4.3\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ\right.}$ |
    |Input of CO~2~ | $meoh_{CO2}$ | $0.075\ \color{grey}{\left.kg\ CO_{2}\middle/MJ_{MeOH}\right.}$ |
    |Input of electricity | $meoh_{el}$ | $0.05\ \color{grey}{\left.MJ_{el}\middle/MJ_{MeOH}\right.}$ |
    |Share of RFNBO in the output | $Share_{RFNBO- MeOH}$ | $91\color{grey}{\%}$ |
    |Conversion rate of CO~2~ | $conv_{CO2}$ | $90\color{grey}{\%}$ |
    
    Total GHG intensity: 
    
    $${CI}_{MeOH} = meoh_{h2} \times CI_{H2} + \frac{meoh_{CO2}}{conv_{CO2}}\ CI_{CO2} + meoh_{el} \times CI_{grid} \approx 6.8\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{MeOH}\right.}$$
        
    
    
??? "Fuel transport"
    ## Fuel transport
    
    ### Emissions
    
    -   Emissions of transport should be allocated based on the emissions attributable to the RFNBO (generally by energy, mass or volume of the overall transported fuel). This includes empty return trips. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q58](../FAQ/faq.md#Q58) 
    
    ### Example in this case study
    
    The ship is loaded with 80% of the methanol produced in this pathway and 20% fossil methanol. The return trip is empty. Transport emissions are calculated by dividing the overall emissions of both trips by the overall fuel transported and allocated by energy to all fuels.

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Emissions caused by transport | $e_{transp}$ | $1\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{fuel\_transported}\right.}$|

    !!! info "Transport emissions calculation"
        In general, the emissions shall be calculated by calculating the overall emissions caused by all transport operations, including empty return trips and fugitive emissions. All emissions, also for upstream fuel production, should be included. They should then be attributed to all transported products.
        
    !!! info "Using the transported fuel"
        If the ship uses part of the transported fuel to propell itself, the amount arriving at destination is lower than the amount charged. In that case, the calculation should obviously take into account the upstream and combustion emissions from the fuel burnt in the ship, in the current example a mix of the RFNBO and fossil methanol, and should allocate them to the amount of fuel that arrives at destination.

    
    Total GHG intensity: ${CI}_{MeOH\_ transported} = {CI}_{MeOH} + e_{transp} \approx 7.8\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{MeOH\_at\_destination}\right.}$
        
    
    
??? "Hydrogen and oxygen production"
    ## Hydrogen and oxygen production
    
    ### Allocation of emissions to products without energy content
    
    -   If oxygen is sold as a product, emissions can be allocated to it by economic value (average factory-gate value of the products over the last three years). [GHG.15](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q49](../FAQ/faq.md#Q49) 
    
    ### Example in this case study

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Mass ratio of oxygen to hydrogen| $m_{O2}$ | $8\ \color{grey}{\left.kg\ {O}_{2}\middle/kg\ H_{2}\right.}$|    
    |Average factory-gate price of hydrogen| $p_{H2}$ | $5\ \color{grey}{\left.\unicode{x20AC}\middle/kg\ H_{2}\right.}$|
    |Average factory-gate price of oxygen| $p_{O2}$ | $0.1\ \color{grey}{\left.\unicode{x20AC}\middle/kg\ O_{2}\right.}$|
    |Total emissions for electrolysis (in this case assumed to be only from electrolysis)|$e_{ely\_aux}$ | $0.5\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{H2}\right.}$|
    
    Allocation of emissions to hydrogen: 
    
    $$alloc_{H2} = \frac{p_{H2}}{p_{O2}m_{O2} + p_{H2}} \approx 86\color{grey}{\%}$$
    
    Emissions attributed to hydrogen: $e_{ely\_ H2} = e_{ely\_aux} \times alloc_{H2} \approx 0.43\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{H2}\right.}$
        
    
    
??? "Use of waste heat"
    ## Use of waste heat
    
    ### Waste heat as rigid input
    
    -   If waste heat from another process is used as energy input, and the waste heat production cannot be increased and does not represent 10% of the economic value or more, it can be considered a rigid input with no emissions attributed to it. [GHG.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q45](../FAQ/faq.md#Q45) 
    
    ### Example in this case study
    
    The heat in the case study can be considered waste heat with no emissions.
    
??? "Final fuel production"
    ## Final fuel production
    
    ### Share of RFNBO in each output stream
    
    -   The share of RFNBO in all outputs should be equal. [RED II 30](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv:OJ.L_.2018.328.01.0082.01.ENG#030.002) [Q-Annex2](https://energy.ec.europa.eu/document/download/21fb4725-7b32-4264-9f36-96cd54cff148_en?filename=2024%2003%2014%20Document%20on%20Certification.pdf)[Q47](../FAQ/faq.md#Q47) [Q51](../FAQ/faq.md#Q51) [Q52](../FAQ/faq.md#Q52) 
    
    ### Share of overall RFNBO in the output
    
    -   If the additional hydrogen is an RFNBO and increases the heating value of the outputs, it also increases the share of RFNBO in the output. [Q53](../FAQ/faq.md#Q53) [Q57](../FAQ/faq.md#Q57) 
    
    ### Other sectors than transport
    
    -   According to the new RED, RFNBO terminology can also be used in other sectors. [RED II rev](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023L2413) [Q10](../FAQ/faq.md#Q10) 
    
    ### Example in this case study
    
    For illustration purposes, the methanol-to-synfuels process is modified and simplified to only produce diesel and kerosene and only use methanol, hydrogen and heat as inputs. In this example, we assume that the heat is not contributing to the heating value of the fuel.

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Energy share of diesel in output| $Share_{diesel}$ | $44\color{grey}{\%}$    |
    |Energy share of kerosene in output| $Share_{kerosene}$ | $56\color{grey}{\%}$  |  
    |Input of methanol| $fuel_{MeOH}$ | $1.1\ \color{grey}{\left.MJ\ MeOH\middle/MJ\ fuel\right.}$    |
    |Input of hydrogen| $fuel_{H2}$ | $0.1\ \color{grey}{\left.MJ\ H_{2}\middle/MJ\ fuel\right.}$    |
    |Share of RFNBO in hydrogen input| $Share_{RFNBO-H2}$ | $100\color{grey}{\%}$    |    
    |Input of heat| $fuel_{heat}$ | $0.2\ \color{grey}{\left.MJ\ heat\middle/MJ\ fuel\right.}$    |
    
    Emissions attributed to all fuels:
    
    $$E = CI_{fuels} = {fuel}_{MeOH} \times {CI}_{MeOH\_transported} + {fuel}_{h2} \times CI_{H2} + {fuel}_{heat} \times CI_{heat} \approx 8.6\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{fuel}\right.}$$
    
    Emission reduction compared to the fossil fuel comparator: 
    
    $$Savings = \frac{E_{F} - E}{E_{F}} = \frac{94 - 8.6}{94} \approx 91\color{grey}{\%}$$

    Share of RFNBO: 
    
    $$Share_{RFNBO-fuels} = \frac{Share_{RFNBO-MeOH} \times {fuel}_{MeOH} + Share_{RFNBO-H2} \times \ {fuel}_{H2}}{{fuel}_{MeOH} + {fuel}_{H2}} \approx 92\color{grey}{\%}$$
    