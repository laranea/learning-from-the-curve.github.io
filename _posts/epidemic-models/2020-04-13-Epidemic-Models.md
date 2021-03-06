---
layout: post
title: COVID-SIR
date: 2020-04-13 13:00:00 +0100
category: Epidemic-Models
---
[Vincenzo Verardi](https://directory.unamur.be/staff/vverardi) (UNAMUR-CRED, FNRS, ULB).

**Table of Contents**:<a name="tbc"></a>

1. [Introduction](#cap1)
2. [Non-intervention](#cap2)
3. [Social distancing](#cap3)
4. [Lockdown](#cap4)
5. [Conclusion](#cap5)

### Introduction <a name="cap1"></a>

[*Back to Table of Contents*](#tbc)

-------------------------------------

In this note, we will look at a very simple model to sketch how the COVID 19 epidemic could evolve over time (focusing on Belgium). We will use a model called \\(SIR\\) (and more precisely its Kermack-McKendrick version). This model could be complexified substantially to incorporate more specificities of the virus and of the transmission mechanism. To simplify things as much as possible, we however prefer to stick for the moment to its simplest version. In a future note we will propose a more elaborate model considering both symptomatic and asymptomatic cases and considering various age classes.

<!--more-->

The \\(SIR\\) model divides the population into three groups of individuals: \\(S\\), \\(I\\) and \\(R\\). Group \\(S\\) is the group of susceptible individuals (i.e. those individuals that are at risk of being contaminated). For the case of COVID-19, at the beginning of the epidemic \\(S\\) is the entire population given that nobody has anti-bodies (it is indeed a new virus for which no vaccine is available). Group \\(I\\) is the group of individuals that have been contaminated recently and that are infectious. Finally, the result or removed group \\(R\\) is the group of individuals that were contaminated but that had an outcome (either a recovery of death). They are not infectious anymore.

The sizes of these groups evolve over time as the virus spreads. The size of S decreases when people get contaminated and move into the infectious group \\(I\\). When individuals recover or die, they then move from the infectious group \\(I\\) to the removed group \\(R\\). The evolution of the sizes of these groups can be modelled by a system of 3 differential equations:

$$ dS/dt=-βSI $$

$$dI/dt=βSI-γI$$

$$dR/dt=γI$$

These variations are very simple to interpret:

The first equation states that the size of \\(S\\) decreases by the number of newly contaminated individuals which is simply the infection rate (\\(β\\)) multiplied by the number of susceptible individuals (\\(S\\)) that encountered infectious individuals (\\(I\\)).

The second equation states that the number of infectious individuals (\\(I\\)) will be increased by the newly contaminated individuals (\\(βSI\\)) minus the previously infectious individuals that had an outcome and moved to group \\(R\\) (i.e. the removal rate γ multiplied by the infectious individuals \\(I\\)).

Finally, the last equation states that the removed group increases by the number of individuals that were infectious that had an outcome (\\(γI\\)). In the case of COVID 19, before the beginning of the epidemic the size of \\(S\\) is the entire population (as nobody is immune to the new virus). Then, once a first individual is contaminated, \\(S\\) decreases by one unit and \\(I\\) increases by one unit. This is the beginning of the dynamic of the epidemic. After some time, this infectious individual contaminates new individuals before recovering (or dying). In the meantime, the newly contaminated individual start spreading the virus and the epidemic starts.

A crucial parameter in an epidemic is the average number of people who will catch a disease directly from one contagious person (this is the so-called reproduction number, generally noted as \\(R\_0\\), which is closely linked to \\(β\\) and \\(γ\\)). In the case of COVID-19, it has been estimated that the reproduction number is approximately 2.7, \\(γ\\) is approximately 0.2 and \\(β\\) is approximately 0.54.

In the subsections here below, we look at the evolution of \\(S\\), \\(I\\) and \\(R\\) over time (days) considering different scenarios (after normalizing the entire population to 1 to work with percentages). Only lines related to group \\(I\\) are activated. The other can be activated by clicking on the legend on their reference.

### Non-intervention <a name="cap2"></a>

[*Back to Table of Contents*](#tbc)

-------------------------------------

In the cases of non-intervention, the virus spreads very quickly. The number of infected individuals increases and at day 50, about 28% of the population is infectious. If 10% of these need to be hospitalized, even for a small country like Belgium results are scary: about 300 000 individuals have to be hospitalized. Knowing that approximately 10% of hospitalized patients will need intensive care, the medical sector is completely overwhelmed (slightly more than 2000 beds are available in intensive cares in Belgium). At the end of the epidemic, 90% of the population will have been contaminated as can be seen in the (plain green) "result" line if activated. The collective immunity will have been reached but the cost in terms of lives would be enormous (remember that is is estimated that the mortality rate of the disease is about 4.5%).

**Click on the legend to add or remove lines**

{% include plots/Epidemic-Models-2020-04-13/LF.html%}

### Social distancing <a name="cap3"></a>

[*Back to Table of Contents*](#tbc)

-------------------------------------

*Social distancing from the beginning (reducing the reproduction number to 1.5) but with no lockdown.*

In the case of social distancing implemented from the beginning of the epidemy, the peak of the infectious individuals is shifted to the right (later in time) and, more importantly, the height is lower (this is the famous "flattening the curve"). Indeed, at day 133 a total of 7% of individuals are infectious. This is however still too much for the medical system as it translates into 77 000 individuals needing hospitalization and almost 8000 needing intensive care. At the end of the epidemic, about 60% of the population will have been contaminated as can be seen in the "result" (plain green) line if activated. Susceptible of being contaminated drops to 40% which guarantees a collective immunity.

**Click on the legend to add or remove lines**

{% include plots/Epidemic-Models-2020-04-13/Flat.html%}

### Lockdown <a name="cap4"></a>

[*Back to Table of Contents*](#tbc)

-------------------------------------

*A lockdown that starts at day 35 after the first contagion and that continues till nobody is infectious anymore.*

In the case of a lockdown (having a visible effect from day 35), the effect is remarkable. The peak (occurring at day 35) will be much lower than in the case of no-intervention or social distancing. Only 2% of the people will need hospitalization which is more or less what the medical sector can handle. However, a lockdown is very costly, and it is probably impossible to keep it for so long. Less than 10% of the population will have been infected by the end of the epidemic leaving the society without any collective immunization.

**Click on the legend to add or remove lines**

{% include plots/Epidemic-Models-2020-04-13/Lockdown.html%}

#### Lockdown and back to normal

-------------------------------------

*A lockdown from day 35 till day 80 (when the epidemic seems under control) and then go back to normal.*

In this case the initial lockdown is very efficient. However once the restrictions are removed at day 80 when the epidemic seems under control, the situation becomes quickly again overwhelming for the medical sector and all the efforts seem vain as the difference with the non-intervention case is marginal. At the end of the epidemic more than 90% of the people will have been infected by the virus and at the peak 22% of the population is affected. The peak has only been moved over time and all the initial efforts are useless. In terms of collective immunization, this scenario is similar to the one without any intervention.

**Click on the legend to add or remove lines**

{% include plots/Epidemic-Models-2020-04-13/Lockdown_restart.html%}

#### Lockdown and social distancing

-------------------------------------

*A lockdown from day 35 till day 80 and then keep long-term social distancing reducing the reproduction number to to 1.5.*

In this case, the initial lockdown is very efficient. Once the restrictions are removed (at day 80) and social distancing guaranteeing a reproduction number of 1.5 or less is imposed, the situation remains under control for the medical sector and guarantees a sustainable long-term effect. At the end, about 40% of the individuals will have been contaminated but on a much longer time span. The collective immunization is good and the costs in terms of lives are moderate

**Click on the legend to add or remove lines**

{% include plots/Epidemic-Models-2020-04-13/Lockdown_socialD.html%}

### Conclusion <a name="cap5"></a>

[*Back to Table of Contents*](#tbc)

-------------------------------------

In this note, we presented a very simple model to illustrate i) how quickly the virus might spread, ii) why public interventions are needed and iii) why a clear and efficient strategy is needed for the exit of the lockdown. In a future note, we will present a more elaborate model where alternative exit strategies are compared.
