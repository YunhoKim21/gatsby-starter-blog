---
layout: post
title: Mixed Strategy Nash Equilibrium 
date: 2022-7-11 14:11:00-0800
description: MSNE
tags: Game thoery
categories: Berkeley
---

## Definition of Mixed Strategy Nash Equilibrium 
- A mixed strategy profile $$\sigma = (\sigma_1, \sigma_2 \dots \sigma_n)$$ is a nash equilibrium if, for each player i, $$\sigma_i$$ is the best response to $$\sigma_{-i}$$
- That is, 
$$u_i(\sigma_i , \sigma_{-i}) \geq u_i(\sigma_i', \sigma_{-i}) \text{ for all } \sigma_i' \text{ and } i$$
- It is sufficent to check all of player i's pure strategies:
$$u_i(\sigma_i , \sigma_{-i}) \geq u_i(s_i, \sigma_{-i}) \text{ for all } s_i \in S_i \text{ and } i$$
- This is because, mixed strategy is only a linear interpolation beteween different strategies. For example, if the strategy a gives expected payoff 10, and strategy b gives expected payoff 15, then mixing between strategy a and be will always give a lower expected payoff than 15, which clearly cannot be a best response. This is the reason we can only care about pure strategies. 
> For a mixed strategy to be a best response, it must put positive probabilites only on pure strategies that are best responses. 

## Example 1 - matching pennies

| | H| T|
|-|-|-|
|H |1, -1 | -1, 1|
|T|-1, 1|1, -1|

- Suppose that payer 2 chooses heads or tails in equal probability. 
- The expected payoff of player 1 is, 
$$u_1(H, (0.5, 0.5)) = 0.5-0.5 = 0$$
$$u_1(T, (0.5, 0.5)) = -0.5 + 0.5 = 0$$
- Notice that the expected payoff is same in either choices, Heads or Tails. 
- This implies that for player 1, there is no incentive to deviate from any mixed strategy, thus any strategy for player 1 is a best response. 
- Assume that player 1 also chooses in equal probability, Then because of the symmetry of the game, we notice that both players are best responding to each other. 
- Thus the mixed strategy profile, $$((0.5, 0.5), (0.5, 0.5))$$ is a maxed strategy nash equilibrium. 

## Example 2 - coordination 

| | A| B|
|-|-|-|
|A|1, 1 |0, 0 |
|B|0, 0 |1, 1 |

- suppose that player 1 chooses A in probability p, and player 2 chooses A in prbability q 
- The expected payoff for player 1 playing A is q, and for playing B, it is 1 - q. 
- If q is 0.5, choosing A or B for player 1 is indifferent. Thus any mixed strategy is a best response. 
- If q is not 0.5, then choosing either A or B is always better than mixed strategy. 
- Note that the same logic applies to player 2. Thus, there are nash equilibriums in this game. 
$$NE = \{((0.5, 0.5), (0.5, 0.5)), ((1, 0), (1, 0)), ((0, 1), (0, 1))\}$$

## Example 3 - Pareto Coordination 

| | A| B|
|-|-|-|
|A|2, 2 |0, 0 |
|B|0, 0 |1, 1 |

- As the example above, suppose that player 1 chooses A in probability p, and player 2 chooses A in prbability q.
- We can first notice that we have two pure nash equilibrium, (A, A) or (B, B).
- The expected payoff for player 1 playing A is 2q, and for playing B, it is 1 - q. 
- Those expected payoff must be equal for mixed strategy nash equilibrium to exist. 
- Thus, p must be 1/3 

## Methodolofy of Finding Mixed Strategy Nash Equilibria 
1. Calculate the set of rationalizable strategies by performing the iterated dominance procedure. 
2. Restricting attention to rationalizable probabilites that make the other player indifferent between the relevant pure strategies. 
3. Solve these equations to determine the equilibrium mixing probabilities. 

## Example 4 - general case 

| | X| Y|
|-|-|-|
|A|0, 5 |4, 3 |
|B|2, 3 |0, 3 |
|C|3, 0|0, 2|

- First step, find for dominated strategy. 
- Strategy B is dominated by mixture of A and C. 
- Thus the reduced table looks like, 

| | X| Y|
|-|-|-|
|A|0, 5 |4, 3 |
|C|3, 0|0, 2|

- Notice that we cannot find any pure strategy nash equilibrium. 
- Suppose player 2 chooses X by probability q. 
- The expected payoff for A is 0q+4(1-q), and 3q+0(1-q) for B. These values should be same. Thus, 4-4q = 3q, p=4/7. 
- Then suppose player 1 chooses A by probability p. 
- The expected payoff for X is 5p+0(1-p), and 3p + 2(1-p) for Y. Thus, 5p = 3p+2-2p, p=1/2. 
- We found out the unique nash equilibrium, 
$$((1/2, 0, 1/2), (4/7, 3/7))$$

## Nash's Theorem

> Every finite game (having a finite number of players and finite strategy space) has at least one Nash equilibrium in pure or mixed strategy. 

## Some properties of Mixed Strategy Nash Equilibrium 
- All pure strategies that are being played in a mixed-strategy Nash 
equilibrium must yield the **same expected payoff**.
- All pure strategies that are not being played in a mixed-strategy 
Nash equilibrium cannot yield a higher payoff.
- Every finite game (having a finite number of players and a finite 
strategy space) has at least one Nash equilibrium in pure or mixed 
strategies. 