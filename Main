# Description: calculate insurance rates
from HSA_config import deduct as hsa_deduct, max as hsa_max, in_cost as hsa_in_cost
from Trad_config import deduct as trad_deduct, max as trad_max, in_cost as trad_in_cost
import matplotlib.pyplot as plt

def Medical(deduct, max, in_cost, cost):
    if deduct >= cost:
        cost = cost
    else:
        cost = cost - deduct
        cost = deduct + (cost * 0.10)
    
    if cost >= max:
        cost = max
    else:
        cost = cost

    cost = cost + (in_cost * 24)
    return cost

# Run for HSA_config
print("Results for HSA_config:")
hsa_costs = []
hsa_results = []
for cost in range(1000, 50001, 100):
    result = Medical(hsa_deduct, hsa_max, hsa_in_cost, cost) - 2000
    hsa_costs.append(cost)
    hsa_results.append(result)
    print(f"Cost: {cost}, Final Total: {result}")

# Run for Trad_config
print("\nResults for Trad_config:")
trad_costs = []
trad_results = []
for cost in range(1000, 50001, 100):
    result = Medical(trad_deduct, trad_max, trad_in_cost, cost)
    trad_costs.append(cost)
    trad_results.append(result)
    print(f"Cost: {cost}, Final Total: {result}")

# Plotting
plt.figure(figsize=(10,6))
plt.plot(hsa_costs, hsa_results, label='HSA_config')
plt.plot(trad_costs, trad_results, label='Trad_config')
plt.xlabel('Medical Cost')
plt.ylabel('Final Total')
plt.title('Insurance Rate Comparison')
plt.legend()
plt.grid(True)
plt.show()
