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
Selects and views saved protocol for heaters. 

Creates control algorithms which allow for the PCR to be run in a cell below. 

Control implementation uses trim PID control, and provides two methods for this PID control.

  Method I: uses feedforward control governed by scipy.linprog and a position PID function.
  
  Method II: uses feedforward control governed by cvxpy and a velocity PID function.
  
  Both controllers were tuned for optimal control at P=1, I=0, D=0.05 using a simulation (hardware malfunction prevented physical testing). 
  
  Start and stop buttons allow user control of the PCR runtime
  
  Results are graphed as the interface runs, including:
  * Temperature setpoint
  * Actual temperature
  * Power of Heaters I and II

## Review UI
Retrieves data from the Runtime UI notebook.

Displays the data recorded from both control algorithms, allowing the user to evaluate which control is appropriate for their use. 
  
Simulation trials found that the cvxpy and velocity PID control reached the desired temperatures more efficiently and accurately.

## Contributions:

Jessi: 
* Drafted the Runtime UI notebook with initial feedforward control (using scipy) and PID control algorithm (position): used 06.02 notebook template and PID using python yield statement
* Tuned the PID control gain values to optimize the simulation (hardware malfunction)
* Created Review UI notebook using information from 06.03 notebook template.

Ana:
* Created Protocol UI notebook with appropriate requirements from project guidelines: used 06.03 notebook template. 
* Created feedforward control algorithm by using cvxpy library and PID control algorithm (velocity). 
* Debugged Runtime UI work function and widgets.
