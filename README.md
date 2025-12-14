# Fast Food Restaurant Queue Simulation using SimPy

## System Description and Performance Goals

This project models a fast-food restaurant queue system using discrete event simulation.  
Customers arrive at the restaurant, wait in a queue if all cashiers are busy, receive service from an available cashier, and then leave the system.

The main performance goals of the system are:
- Minimize customer waiting time
- Reduce average queue length
- Maintain high throughput
- Ensure healthy cashier utilization
- Serve the maximum number of customers during operating hours

---

## Modeling Approach and Assumptions

The system is modeled using **SimPy**, a discrete-event simulation library in Python.

Key assumptions:
- Customer arrivals follow an exponential distribution
- Service times follow an exponential distribution
- Customers are served on a first-come, first-served basis
- No customer leaves the queue without being served
- Cashiers work continuously without breaks
- Simulation time is fixed to 120 minutes

---

## Data Description and Methodology

Real operational data is provided in `dataset.csv`.  
The dataset contains the following columns:

- `Arrival_Time`
- `Service_Start_Time`
- `Service_End_Time`
- `Cashier_ID`

From this dataset:
- Average arrival interval is calculated using total time and number of customers
- Average service time is calculated from service start and end times
- These real values are used as input parameters for the simulation

The real data is used only to derive parameters.  
All scenario experiments are conducted using simulated data.

---

## Detailed Analysis and Findings

Four scenarios were analyzed using the simulation model.

### Base Case (2 Cashiers – Normal Demand)

This scenario represents the current operating condition.  
The system shows moderate waiting times and queue lengths.  
Cashier utilization is high, indicating that the system is close to saturation.

### More Cashiers (3 Cashiers – Normal Demand)

Adding one extra cashier reduces average waiting time and queue length.  
Throughput improves slightly, while utilization decreases to a safer level.  
This scenario shows better service efficiency and customer experience.

### Peak Time (2 Cashiers – High Demand)

During peak hours, customer arrivals increase significantly.  
With only two cashiers, long queues form and waiting times become high.  
Cashier utilization exceeds acceptable limits, indicating system overload.

### Peak Time with More Cashiers (3 Cashiers – High Demand)

Introducing an additional cashier during peak periods improves system performance.  
Waiting time and queue length are reduced compared to the peak-time base case.  
This confirms that dynamic staffing helps manage high demand effectively.

Overall, the results show that system performance is strongly influenced by arrival rate and number of cashiers.

---

## Output Tables

The simulation generates a summary table comparing all scenarios.  
This table includes:
- Average waiting time
- Average queue length
- Throughput
- Cashier utilization
- Percentage of customers served

The output table is displayed in the console after simulation execution.

---

## Visualizations

The following graphs are generated automatically by the simulation:
- Average Waiting Time per Scenario
- Average Queue Length per Scenario
- Throughput per Scenario
- Cashier Utilization per Scenario
- Percentage of Customers Served

All visualizations are saved as PNG files in the project directory.

---

## Limitations and Future Extensions

### Limitations
- Customer impatience is not modeled
- Only exponential distributions are used
- Cashier breaks are not considered
- Single queue system only

### Future Extensions
- Introduce customer abandonment and balking
- Add priority customers
- Model multiple service counters
- Extend simulation duration
- Add a graphical dashboard

---

## How to Run the Project

```bash
pip install simpy pandas matplotlib
python restaurant_queue_simulation.py

```
👩‍💻 Author
M.Z.F. Zazna
Bachelor of Software Engineering
Open University of Sri Lanka
