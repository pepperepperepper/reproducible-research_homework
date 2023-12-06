# Reproducible research: version control and R

### Question 4

**a.**  
The .R script provided contains the code to write the random_walk() function. The random_walk() function creates a data frame and fills it with positions based on randomly generated angles for multiple iterations. This simulates the random walk. random_walk was run twice and produces two data frames (data1 and data2), each with 500 steps (i.e. 500 iterations). 

The walks are visualised graphically by plotting both data1 and data2. The grid.arrange() function places the two graphical visualisations of the two walks next to each other. The graphs show the walks in two dimensions (in a grid with a x and y-axis). The direction of the path is indicated by the colour gradient; dark blue represents when t is small/the earlier steps, and light blue represents when t is larger/the later steps. Therefore, the path moves from dark blue to light blue.

The random_walk() function produces a new data frame each time, i.e. re-running the random_walk(500) makes a different data1 and data2 and therefore different paths each time. Executing the whole code repeatedly creates new, random pairs of graphs each time.

**b.**  
A random seed is the starting point for generating random numbers in functions in R. When R generates random numbers, the numbers are not truly random but instead are pseudorandom numbers. It is pseudorandom because the algorithm that is used to generate the randomness uses a ‘seed’ to initialise it. The seed is randomly selected and therefore a random outcome is produced. This is stored in .Random.seed in the global environment and is a vector of integers (Random-R documentation, n.d). 

However, knowing this seed means that the random numbers can be predicted and therefore reproduced. Setting the same random seed means that the same sequence of random numbers is generated each time. Crucially, setting seed is important for reproducibility because the exact same results–despite being random–are produced each time. Therefore, the code can be run by another person and they can achieve the exact same outcome. Setting a random seed is important for other functions, e.g. debugging a code (setting a seed would make it easier to identify errors by removing the element of randomness) (r-coder.com, n.d).

The random seed can be set with the function: set.seed(n) from the base R package. Sharing the value, n, used in set.seed(n) allows random number generation to be reproduced.

**c.**
Please see the script and part d. for the edits. 

**d.**
Below are images of the latest commit in the comparison view.
<img width="1434" alt="Screenshot 2023-12-06 at 19 15 15" src="https://github.com/pepperepperepper/reproducible-research_homework/assets/150150609/03ebbd7a-f24a-4f48-9808-7cdb25413c23">
<img width="1434" alt="Screenshot 2023-12-06 at 19 15 38" src="https://github.com/pepperepperepper/reproducible-research_homework/assets/150150609/6aa04b9d-7e0f-426a-8e63-98c7c63f98d3">




**References**

r-coder.com, 'Setting the Seed in R for Reproducibility'. 
Available at: https://r-coder.com/set-seed-r/ (Accessed: 6 December 2023).

R Project for Statistical Computing, 'Random - R Documentation'. Available at: https://stat.ethz.ch/R-manual/R-devel/library/base/html/Random.html (Accessed: 6 December 2023).


## Instructions

The homework for this Computer skills practical is divided into 5 questions for a total of 100 points (plus an optional bonus question worth 10 extra points). First, fork this repo and make sure your fork is made **Public** for marking. Answers should be added to the # INSERT ANSWERS HERE # section above in the **README.md** file of your forked repository.

Questions 1, 2 and 3 should be answered in the **README.md** file of the `logistic_growth` repo that you forked during the practical. To answer those questions here, simply include a link to your logistic_growth repo.

**Submission**: Please submit a single **PDF** file with your candidate number (and no other identifying information), and a link to your fork of the `reproducible-research_homework` repo with the completed answers. All answers should be on the `main` branch.

## Assignment questions 

1) (**10 points**) Annotate the **README.md** file in your `logistic_growth` repo with more detailed information about the analysis. Add a section on the results and include the estimates for $N_0$, $r$ and $K$ (mention which *.csv file you used).
   
2) (**10 points**) Use your estimates of $N_0$ and $r$ to calculate the population size at $t$ = 4980 min, assuming that the population grows exponentially. How does it compare to the population size predicted under logistic growth? 

3) (**20 points**) Add an R script to your repository that makes a graph comparing the exponential and logistic growth curves (using the same parameter estimates you found). Upload this graph to your repo and include it in the **README.md** file so it can be viewed in the repo homepage.
   
4) (**30 points**) Sometimes we are interested in modelling a process that involves randomness. A good example is Brownian motion. We will explore how to simulate a random process in a way that it is reproducible:

   - A script for simulating a random_walk is provided in the `question-4-code` folder of this repo. Execute the code to produce the paths of two random walks. What do you observe? (10 points)
   - Investigate the term **random seeds**. What is a random seed and how does it work? (5 points)
   - Edit the script to make a reproducible simulation of Brownian motion. Commit the file and push it to your forked `reproducible-research_homework` repo. (10 points)
   - Go to your commit history and click on the latest commit. Show the edit you made to the code in the comparison view (add this image to the **README.md** of the fork). (5 points)

5) (**30 points**) In 2014, Cui, Schlub and Holmes published an article in the *Journal of Virology* (doi: https://doi.org/10.1128/jvi.00362-14) showing that the size of viral particles, more specifically their volume, could be predicted from their genome size (length). They found that this relationship can be modelled using an allometric equation of the form **$`V = \beta L^{\alpha}`$**, where $`V`$ is the virion volume in nm<sup>3</sup> and $`L`$ is the genome length in nucleotides.

   - Import the data for double-stranded DNA (dsDNA) viruses taken from the Supplementary Materials of the original paper into Posit Cloud (the csv file is in the `question-5-data` folder). How many rows and columns does the table have? (3 points)
   - What transformation can you use to fit a linear model to the data? Apply the transformation. (3 points)
   - Find the exponent ($\alpha$) and scaling factor ($\beta$) of the allometric law for dsDNA viruses and write the p-values from the model you obtained, are they statistically significant? Compare the values you found to those shown in **Table 2** of the paper, did you find the same values? (10 points)
   - Write the code to reproduce the figure shown below. (10 points)

  <p align="center">
     <img src="https://github.com/josegabrielnb/reproducible-research_homework/blob/main/question-5-data/allometric_scaling.png" width="600" height="500">
  </p>

  - What is the estimated volume of a 300 kb dsDNA virus? (4 points)

**Bonus** (**10 points**) Explain the difference between reproducibility and replicability in scientific research. How can git and GitHub be used to enhance the reproducibility and replicability of your work? what limitations do they have? (e.g. check the platform [protocols.io](https://www.protocols.io/)).
