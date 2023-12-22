# Traveling-Sales-Person-Optimization
Solved traveling sales person optimization problem for a delivery company in Python using Gurobi.

# Business Problem
Route optimization plays a pivotal role in the efficiency and success of delivery operations. By employing advanced algorithms and real-time data analysis, route optimization ensures that delivery trucks take the most time-efficient and cost-effective paths to reach their destinations. This not only minimizes operational costs, but contributes to timely deliveries, enhancing customer satisfaction and loyalty. In an industry where speed and reliability are pivotal, solving the business problem of inefficient routes through optimization is not just a strategic competitive advantage, but a necessity.

**Why is this important?**
* By minimizing the time taken to deliver packages, delivery companies can increase efficiency, in turn heightening customer satisfaction and loyalty
* The minimization of costs benefits the company overall

# Data Used
The data used in this project was fictional data of the locations of 500 packages. Each package's location is represented with an (x,y) coordinate, with (0,0) representing the distribution center.

# Approach
Gurobi is an optimization software library in Python that uses mathematical optimization to solve problems. It allows you to set an objective function with decision variables, create constraints, and find an optimal solution. In this specific problem, I have 10 available trucks to deliver a total of 500 packages. The project begins by assigning packages to trucks using 2 methodologies:
1. K-means clustering
2. 3-change simulated annealing
   
First, I conducted **k-means clustering** with k=10 to assign packages to each of the 10 trucks. I then ran a TSP optimization problem for each truck and computed the total distance. Next, I performed **3-change simulated annealing** which can be outlined in the following process: 1) Initialize a loop completely at random. 2) Toss a fair coin and pick randomly between a reverse and transport change. 3) Try the change. 4) If it reduces the total distance traveled keep the change and go back to 2; if the change does not decrease the distance traveled don’t keep it and go back to 2. For the remainder of the project, I used the methodology that resulted in the shortest Euclidean distance.
