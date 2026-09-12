[[Cloud Applications/Unit 1]]
Private servers needed at peak = 4000/80 = 50 servers
25% headroom = 50 x (1+0.25) = 62.5 ~ 63 Servers
Exact cost (62.5 servers): 62.5 x 180 = $11,250
Rounded (63 servers): 63 x 180 =  $11,340

Public base = 1200/80 = 15 instances
public peak = 4000/80 = 50 instances
35 Buffer neeeded
Base Cost = 15 x 24 hours = 360 hours/day
Burst Cost = 35 x 4 = 140 hours/day
Monthly volume = (360+140) x 30 days = 15000 hours
Monthly Cost = 15000 x 0.12 = $1800

Surge extra = 4000 - 1200 = 2800 reqs/day
SLA penalty = 2800 x 180 = 504,000 reqs
daily penalty = 504000 x 0.00015 = $75.60
Monthly penalty = $75.60 x 30 = $2,268
TOTAL montly = 2268+1800 = $4068

4 hours 20 minutes = 4.3 hours/day
basline = 15x24=360 instances 
peak = 35 x 4.33 hours = 151.67 
monthly = (360 + 151.67)x30 = 15350 
MONTHLY Cost = 15350 x 0.12 = $1,842
SLA Penalty = 0

Savings = ((Private Cloud Cost - Predictive Public Cost)/Private Cloud Cost)x100
Savings = (($11340-$1842)/$11340)x100
= 83.67%