# POLICY EVALUATION

## AIM
To evaluate and compare different policies in the Frozen Lake environment and find the best policy for reaching the goal successfully.

## PROBLEM STATEMENT
In the Frozen Lake environment, an agent must navigate from the start to the goal while avoiding holes. Movements are uncertain due to slipperiness. A policy guides the agent’s actions, but not all policies are effective. The task is to:

Evaluate a given policy (V1) using policy evaluation. Create and test a new policy (V2) to improve performance. Compare both policies based on success rate and rewards. Find the best policy for safely reaching the goal. This helps in identifying the most efficient way to complete the task.

## POLICY EVALUATION FUNCTION

```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V=np.zeros(len(P))
      for s in range(len(P)):
        for prob,next_state,reward,done in P[s][pi(s)]:
           V[s]+=prob*(reward+gamma *prev_V[next_state]*(not done))
      if np.max(np.abs(prev_V-V))<theta:
        break
      prev_V=V.copy()
    return V
```

## OUTPUT:
## Policies:
 ![image](https://github.com/user-attachments/assets/af6d3101-8b04-46b4-aa78-41164b53fec9)
![image](https://github.com/user-attachments/assets/ddad65ad-b9d0-4501-a6af-81c5cd8c315f)
![image](https://github.com/user-attachments/assets/94e145bd-228e-4eaf-bd16-b7f868fb3399)
![image](https://github.com/user-attachments/assets/ac0632f4-8bed-46dd-a8ce-64e7efceaadc)


## State value function:
![image](https://github.com/user-attachments/assets/ab43fc93-1dc3-475a-bdc1-3add99b01c81)
## Best policy:
![image](https://github.com/user-attachments/assets/226da61a-f69f-4bff-a426-ffcb6c4aa63c)




## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.
