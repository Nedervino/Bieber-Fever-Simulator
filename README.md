# Bieber Fever Simulator
This program simulates outbreaks of Bieber Fever, using a mathematical model from the paper 
“A mathematical model of Bieber Fever: The most infectious disease of our time?” , published by 
mathematicians Valerie Tweedle and Robert J Smith. The model from the paper was adapted to represent individual agents
instead of an entire population, to allow for an evolutionary systems implementation of the simulation.
The program was inspired by the course Collective Intelligence, as taught on the VU University Amsterdam, and the resulting research paper (co-written with Bushra Malik) for this course is included in the repository.
<br>

![alt tag](/../screenshots/SQ3nsBS5IR.gif?raw=true)

### How It Works
The model described in the paper (http://mysite.science.uottawa.ca/rsmith43/bieberfever.pdf) uses a variation of the classical SIR Model (Susceptible, Infectious, Recovered) for epidemics. The population can fall in either of these three states, and at the start of the simulation 99 percent of the population is initiated as susceptible (gray), while 1 percent is initiated as (Bieber-)infected (red). Recovered agents are shown in green. People can either enter another state by direct contact with others, through outside influence of either positive or negative media, or cure from the disease naturally; getting bored of Bieber. The biggest variation on the SIR model is the fact that recovered agents can always flow back to a succeptible state, preventing the fever from dying out naturally. Furthermore, there is a continuous inflow of new succeptible agent entering the population, as they grow into the age category where Bieber Fever can occur, and a continous outflow of agents as they reach the age where no sane individual will remain a liking for Justin Bieber.

#####The density of the population
Population density will remain constant during the simulation, with the total number of maturing agents equaling the number of succeptible agents entering on a weekly basis.

#####Model Adaptation
The model was rewritten to apply to individual agents instead of an entire population, to make the model representable as an Evolutionary System. Week-based evaluation was chosen instead of month-based, to show development within a smaller timeframe. Furthermore, the addition of fluctuations in media allowed for a deeper analysis of the effect of various types and progression of media on the epidemic.

#####Media
Three types of media attention were chosen as outside influence on the development of the disease. 
The total absence of media, a positive media peak followed by persevering negative media (also known as the Lindsay Lohan effect), and normal media (in which positive media outweighs negative media). 
These cases were implemented using arrays containing the number of influential stories per week, for the duration of 10 years. After these 10 years the arrays loop. Both positive and negative media have their own array, as represented in the Media Coverage graph next to the simulation.

#####Constants
The following constants hard-coded in our model equal the constants used in the published paper, and are as follows:
Recruitment rate: 10 people month^-1 (on a population of 1500) 
Transmission rate: 8.3*10^-4 people^-1 month^-1 
Maturation rate: (population size / recruitement-rate)*10^-1
All constants were rewritten to week^-1

#####Variables
The following variables can be altered during the simulations:<br>
number-people: Number of agents in the population <br>
boredom-rate: Time before agent loses interest without outside influence <br>
media-coverage: Type of media coverage <br>
ε: The proportion between effectiveness of positive and negative media.

#####Duration of infectiousness
By adjusting the variables and analysing both population graph and the population monitors in the bottom left corner, we can find whether Bieber Fever can disappear at all, what equilibria may occur under certain conditions, and if (ideally) there are conditions allowing for Bieber Fever to die out, whether certain equilibria will occur.
<br>
### How To Use It
Each “tick” represents a week in the time scale of this model.<br>
The NUMBER-PEOPLE slider controls the starting size of the population<br>
BOREDOM-RATE sets the rate at which people become bored out of their own<br>
The SETUP button resets the graphics and plots and randomly distributes NUMBER-PEOPLE in the view. 1% of the population is set to Bieber-infected, the rest to succeptible.<br>
The GO button starts the simulation and the plotting function.<br>
ε sets the ratio to which positive media is more effective than negative media. (0.5 means equal effectiveness, 0.75 means positive media is three times more effective than negative, etc.)<br>
The TURTLE-SHAPE chooser controls whether the people are visualized as person shapes or as circles.<br>
The MEDIA-COVERAGE chooser controls the type of media attention throughout the simulation. Each option (absence of media, positive peak followed by negative, and normal media) loops after 10 years.<br>
The six output monitors show how the population is divided over the three states, and the number of years that have passed. The plot shows (in their respective colors) the number of susceptible, infected, and recovered people. It also shows the number of individuals in the total population in blue.<br>


![alt tag](https://github.com/Nedervino/Quesine-App/blob/master/screenshots/screenshot1.png)
![alt tag](https://github.com/Nedervino/Quesine-App/blob/master/screenshots/screenshot3.png)
