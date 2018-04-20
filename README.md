# Learning


from random import random

initial = 1000

moneyA = [initial]
moneyB = [initial]
wagers = [initial/5]
n = 0


while moneyA[-1] > 0:
    if random() < 0.6:
        moneyA.append(moneyA[-1]+wagers[-1])
        print('Win, win amount ', wagers[-1], ' current balance ', moneyA[-1])
        wagers.append(moneyA[-1]/5)
        print('New wager ', wagers[-1])

    else:
        moneyA.append(moneyA[-1]-wagers[-1])
        print('Lose, lost amount ', wagers[-1], ' current balance ', moneyA[-1])
    n += 1

print('number of simulation ', n)



"""
import numpy as np

def heads_in_a_row(flips, p, want):
    a = np.zeros((want + 1, want + 1))
    for i in range(want):
        a[i, 0] = 1 - p
        a[i, i + 1] = p
    a[want, want] = 1.0
    return np.linalg.matrix_power(a, flips)[0, want]

print(heads_in_a_row(flips=100000, p=4.0 / 10.0, want=5))
"""
