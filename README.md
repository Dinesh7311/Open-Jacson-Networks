DATE:10.03.26

# Series Queues with infinite capacity - Open Jackson Network

## Aim :
To find (a) average number of materials in the system (b) average number of materials in the each conveyor of (c) waiting time of each material in the system (d) waiting time of each material in each conveyor, if the arrival  of materials follow Poisson process with the mean interval time 12 seconds, service time of  lathe machine in series follow exponential distribution  with service time  1 second, 1.5 seconds and 1.3 seconds respectively and average service time of robot is 7 seconds.

## Software required :
Visual components and Python

## Theory

![image](https://user-images.githubusercontent.com/103921593/203239736-7b81f599-71a8-4ae7-b63e-5d98acd9ea54.png)


## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203239789-bc870dce-6727-487b-a0e2-4fc3f5114889.png)


## Program
```python
# Open Jackson Network - Series Queues

arrival_interval = 12
lam = 1/arrival_interval

service_times = [1, 1.5, 1.3, 7]

print("Arrival rate =", lam)

Ls_total = 0
W_total = 0

for i, s in enumerate(service_times):
    mu = 1/s
    
    Ls = lam/(mu-lam)
    Lq = (lam**2)/(mu*(mu-lam))
    
    Ws = Ls/lam
    Wq = Lq/lam
    
    Ls_total += Ls
    W_total += Ws
    
    print("\nServer", i+1)
    print("Service rate =", mu)
    print("Average number in queue =", Lq)
    print("Average number in system =", Ls)
    print("Waiting time in queue =", Wq)
    print("Waiting time in system =", Ws)

print("\nTotal materials in system =", Ls_total)
print("Total waiting time in system =", W_total)
```


## Output
<img width="1691" height="883" alt="image" src="https://github.com/user-attachments/assets/5a9d5b25-b216-499f-9f9a-d8a83a8bccb2" />


## Result
Thus the Series Queue System (Open Jackson Network) was analyzed using Python.

GITHUB LINK:
ithub.com/Dinesh7311/Open-Jacson-Networks
