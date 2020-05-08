# Controls Final Project by Ana Diederich and Jessi Dirksen

## Protocol UI
Determines user settings for both heaters and saves settings to PCR/HeaterProtocol.csv.
User settings include:
* Ambient temperature
* Heating rate
* Cooling rate
* Number of cylces
* Initial denaturation temperature and duration
* Denaturation temperature and duration
* Annealing temperature and duration
* Extension temperature and duration
* Final extension temperature and duration

## Runtime UI
Selects and views saved protocol for heaters. Creates control algorithms which allow for the PCR to be run in a cell below. Control implementation uses trim PID control, and provides two methods for this PID control. The first method uses feedforward control goverened by scipy.linprog and a position PID function. The second method uses feedforward control goverened by cvxpy and a velocity PID function. Both controllers were tuned for optimal control at P=1, I=0, D=0.05 using a simulation (hardware malfunction prevented physical testing.) A start and stop button is created to commence PCR and displays results below.

## Review UI
Retrieves data from the Runtime UI notebook and displays the data recorded from both control algorithms. This allows the user to evaluate which control is appropriate for their use. Our simulation trials found that the cvxpy and velocity PID control reached our desired temperatures more efficiently and accurately.


## Contributions:

Jessi: 
* Drafted the Runtime UI notebook with initial feedforward control (using scipy) and PID control algorithm (position): used 06.02 notebook template and PID using python yield statement
* Tuned the PID control gain values to optimize the simulation (hardware malfunction)
* Created Review UI notebook using information from 06.03 notebook template.

Ana:
* Created Protocol UI notebook with appropriate requirements from project guidelines: used 06.03 notebook template. 
* Created feedforward control algorithm by using cvxpy library and PID control algorithm (velocity). 
* Debugged Runtime UI work function and widgets.
