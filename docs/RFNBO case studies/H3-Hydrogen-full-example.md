# H3: Hydrogen full example

-   System boundaries
-   Where to find more information

![](../images/h3_hydrogen.svg)


??? "Renewable electricity production"
    ## Renewable electricity production
    
    ### Requirements to qualify as renewable
    
    -   **Direct connection** if renewable production generating installation came into operation not earlier than 36 months before the installation producing renewable liquid and gaseous transport fuel of non-biological origin [ADD.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_3) [Q12](../FAQ/faq.md#Q12) [Q13](../FAQ/faq.md#Q13) [Q14](../FAQ/faq.md#Q14) 
    
    -   In a **bidding zone** where the average proportion of **renewable electricity exceeded 90%** in the previous calendar year (and for the five following years). Limited to $\text{full load hours} < 8760\;h  \times \text{RES-E share}$ [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4) [Q15](../FAQ/faq.md#Q15) [Q16](../FAQ/faq.md#Q16) [Q17](../FAQ/faq.md#Q17) 
    
    -   In a **bidding zone** where the **emission intensity of electricity is lower than** $18\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$  with renewable PPAs and temporal and geographical correlation [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4)
    
    -   During **imbalance settlement period** [ADD.4](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_4) [Q18](../FAQ/faq.md#Q18) 
    
    -   If additionality, temporal correlation and geographical correlation are met [ADD.5](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_5) [ADD.6](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_6) [ADD.7](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_7) [Q19](../FAQ/faq.md#Q19) [Q20](../FAQ/faq.md#Q20) [Q21](../FAQ/faq.md#Q21)  [Q22](../FAQ/faq.md#Q22) [Q23](../FAQ/faq.md#Q23) [Q24](../FAQ/faq.md#Q24) [Q25](../FAQ/faq.md#Q25) [Q26](../FAQ/faq.md#Q26) [Q27](../FAQ/faq.md#Q27) [Q28](../FAQ/faq.md#Q28) [Q29](../FAQ/faq.md#Q29) 
    
    ### Combination of options
    
    -   All sourcing options can be combined, but if electricity is used in a time period that does not qualify as renewable, a share of the output equal to this electricity share in the inputs will not be an RFNBO. [Q30](../FAQ/faq.md#Q30) 
    
    ### What electricity inputs are considered
    
    -   To define the share of RFNBO produced, the share of electricity that counts as renewable in all relevant inputs is considered. Relevant inputs are inputs contributing to the energy content of the fuel. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q59](../FAQ/faq.md#Q59) [Q60](../FAQ/faq.md#Q60) [Q65](../FAQ/faq.md#Q65) [Q66](../FAQ/faq.md#Q66) 
    
    ### Temporal aspects
    
    -   Temporal correlation of renewable electricity production and RFNBO production is necessary if they are not connected through a direct connection.
    
    -   The time period over which a “batch” of fuel (with the same GHG intensity) is produced can be up to one month, but needs to be in line with the requirements applying for temporal correlation. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q65](../FAQ/faq.md#Q65) 
    
    ### Geographical aspects
    
    -   Geographical correlation of renewable electricity production and RFNBO production is necessary if they are not connected through a direct connection.
    
    -   Geographical correlation is given if electricity producer and electrolyser are in the same bidding zone, or in an interconnected bidding zone while the electricity price in the zone with the electrolyser is lower than in the interconnected bidding zone, or the renewable energy is produced in an interconnected offshore bidding zone. [ADD.7](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1184#art_7)
    
    ### Example in this case study
    
    Renewable electricity is sourced in the third country via a direct connection and a PPA with additionality, temporal and geographical correlation are met. The relevant time period considered is one month.

    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Total GHG intensity | $CI_{ren}$ | $0\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ_{el}\right.}$ |
        
    
    
??? "Grid electricity"
    ## Grid electricity
    
    ### Grid electricity used in electrolyser
    
    -   If grid electricity is used in the same time period as renewable electricity, the output contains a share of RFNBO and a share of (low-carbon) fuel proportional to the energy input. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    -   The GHG intensity of grid electricity can be calculated using the methodology in [C](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#d1e825-23-1)
    
    ### Auxiliaries powered by grid electricity
    
    Auxiliaries can be powered by grid electricity. The emission intensity of this electricity has to be taken into account, but the share of RFNBO in the output is not affected. [GHG.3](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q11](../FAQ/faq.md#Q11) 
    
    ### Example in this case study
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Total GHG intensity | $CI_{grid}$ | $100\ \color{grey}{\left.g\,CO_2\,eq\middle/kWh_{el}\right.}$ |
        
??? "Water desalination"
    ## Water desalination
    
    ### System boundaries, relevant inputs
    
    As the energy used to desalinate seawater is not adding to the heating value, it is not considered a "relevant input". So it doesn't change the content of RFNBO in the final fuel.

    But it has to be taken into account to calculate the GHG emissions.
    
    ### Example in this case study

    To simplify, it is considered that only fully renewable electricity is used in the process, so there are no GHG emissions.

    
??? "Electrolysis"
    ## Electrolysis
    
    ### Share of RFNBO
    
    The share of RFNBO is calculated for each processing step based on the share of the relevant energy inputs. [GHG.8](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    ### GHG intensity
    
    -   All fuel outputs have the same GHG intensity [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1) [Q53](../FAQ/faq.md#Q53) 
    
    -   The GHG intensity is calculated by dividing all emissions by the overall energy in the fuel. [GHG.1](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1)
    
    ### Example in this case study
    
    The relevant time period considered is one month.
    
    | Parameter                   |    Symbol          | Example value |
    |----------------------------|:--------------:|:-----------------------:|
    |Relevant renewable electricity used | $el_{ren}$ | $500\ \color{grey}{GWh}$ |
    |Relevant grid electricity used | $el_{grid\_ely}$ | $50\ \color{grey}{GWh}$ |
    |Grid electricity for auxiliaries | $el_{grid\_aux}$ | $0.5\ \color{grey}{GWh}$ |
    |Efficiency of the electrolyser | $\eta_{ely}$ | $60\color{grey}{\%}$ |
    
    Total GHG intensity: 
    
    $${CI}_{H2} = \frac{\left( {el}_{grid\_ely} + el_{grid\_aux} \right) \times CI_{grid}}{\left( el_{ren} + {el}_{grid\_ely} \right) \times \eta_{ely}} \approx 4.3\ \color{grey}{\left.g\,CO_2\,eq\middle/MJ\right.}$$
    
    Share of RFNBO in the output:  $Share_{RFNBO-H2}  \frac{el_{ren}}{el_{ren} + {el}_{grid\_ely}} \approx 91\%$
    
??? "Oxygen as a co-product"
    ## Oxygen as a co-product
    
    ### Allocation for products with no energy content
    
    Emissions can be allocated to the co-products by the economic value (because oxygen has no energy content) [GHG.15(f)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32023R1185&qid=1706886791166#anx_1).

    For details on the calculation, see [Co-products case study](#h1-co-products)
    
    ### Example in this case study

    To simplify, it is considered that oxygen is not sold.

