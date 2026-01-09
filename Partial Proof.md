1. Formal setup for KAD theory

We define a minimal mathematical universe to host KAD.

Time:

We have a nonempty set of times

𝑇
with a strict total order 
(
𝑇
,
<
)
.

World states (reality):

There is a nonempty set of possible world states

𝑊
and a function

𝑅
:
𝑇
→
𝑊
where 
𝑅
(
𝑡
)
 is “the state of reality at time 
𝑡
.”

Agents:

There is a nonempty set of agents

𝐴
(humans, robots, systems).

Domains:

There is a nonempty set of domains

𝐷
where a domain is an abstract condition/configuration that affects perception.

Agent’s active domain over time:

Each agent 
𝑎
∈
𝐴
 has a domain trajectory

𝑑
𝑎
:
𝑇
→
𝐷
so 
𝑑
𝑎
(
𝑡
)
 is the domain of agent 
𝑎
 at time 
𝑡
.

Information in reality:

There is a set of information items

𝐼
and a function

I
n
f
o
:
𝑊
→
𝑃
(
𝐼
)
where 
I
n
f
o
(
𝑤
)
 is the set of information present in world state 
𝑤
.

Data collected by agents:

Each agent has a data stream

D
a
t
a
𝑎
⊆
𝑇
×
𝐼
where 
(
𝑡
,
𝑖
)
∈
D
a
t
a
𝑎
 means “agent 
𝑎
 has collected information item 
𝑖
 at time 
𝑡
 as data.”

Now we encode domain‑permission and perception with a key primitive:

Visibility predicate:

A function

V
i
s
:
𝐴
×
𝐷
×
𝑊
×
𝐼
→
{
0
,
1
}
where 
V
i
s
( 𝑎 , 𝑑 , 𝑤 , 𝑖 ) = 1

 means:
“For agent 
𝑎
, in domain 
𝑑
, in world state 
𝑤
, information item 
𝑖
 is perceptually visible.”

This gives us a clean structure to derive assumptions from.

2. Assumption 1 — Domain Permission Assumption
Verbal form (KAD):  
Data collection only occurs when the domain allows it. If the domain blocks perception, the observer cannot collect data even if information is present.

2.1 Formal statement
For each agent 
𝑎
∈
𝐴
 and time 
𝑡
∈
𝑇
:

If 
(
𝑡
,
𝑖
)
∈
D
a
t
a
𝑎
, then:

𝑖
∈
I
n
f
o
(
𝑅
(
𝑡
)
)
 (the information exists in reality at that time), and

V
i
s
(
𝑎
,
𝑑
𝑎
(
𝑡
)
,
𝑅
(
𝑡
)
,
𝑖
)
=
1
 (the active domain permits visibility of 
𝑖
).

Formally:

∀
𝑎
∈
𝐴
,
∀
𝑡
∈
𝑇
,
∀
𝑖
∈
𝐼
:
(
𝑡
,
𝑖
)
∈
D
a
t
a
𝑎
  
⟹
  
(
𝑖
∈
I
n
f
o
(
𝑅
(
𝑡
)
)
∧
V
i
s
(
𝑎
,
𝑑
𝑎
(
𝑡
)
,
𝑅
(
𝑡
)
,
𝑖
)
=
1
)
.
This is the domain‑permission assumption in mathematical form.

2.2 Derivation from more primitive axioms
We introduce two very basic, intuitive axioms about data:

Axiom D1 (Data requires existence):

∀
𝑎
,
𝑡
,
𝑖
:
 
(
𝑡
,
𝑖
)
∈
D
a
t
a
𝑎
  
⟹
  
𝑖
∈
I
n
f
o
(
𝑅
(
𝑡
)
)
.
Data is always about information that actually exists in reality at that time.

Axiom D2 (Data requires visibility):

∀
𝑎
,
𝑡
,
𝑖
:
 
(
𝑡
,
𝑖
)
∈
D
a
t
a
𝑎
  
⟹
  
V
i
s
(
𝑎
,
𝑑
𝑎
(
𝑡
)
,
𝑅
(
𝑡
)
,
𝑖
)
=
1.
An agent can only record as data what is visible to it in its current domain.

These two axioms are extremely weak and natural:
we cannot collect data about something that doesn’t exist, and we cannot collect data about something you cannot see (in your domain).

2.3 “Proof” that Assumption 1 holds
Proposition (Domain Permission):  
Under Axioms D1 and D2, KAD Assumption 1 holds.

Proof:  
Let 
𝑎
∈
𝐴
, 
𝑡
∈
𝑇
, 
𝑖
∈
𝐼
 and suppose 
(
𝑡
,
𝑖
)
∈
D
a
t
a
𝑎
.
By Axiom D1, we have 
𝑖
∈
I
n
f
o
(
𝑅
(
𝑡
)
)
.
By Axiom D2, we have 
V
i
s
(
𝑎
,
𝑑
𝑎
(
𝑡
)
,
𝑅
(
𝑡
)
,
𝑖
)
=
1
.
These two conditions are exactly the formal content of the Domain Permission Assumption.

Thus, Assumption 1 is not a primitive axiom; it is a theorem of the more basic axioms D1 and D2. 

3. Assumption 2 — Reality is continuous (independent of observation)
Our verbal version had two strong components:

Reality exists and evolves independent of observation.

Reality is continuous (in the sense that it doesn’t “stop” when nobody looks).

To avoid unnecessary physical claims, I’ll treat “continuous” here as:

reality is defined for all times, independent of whether someone is observing.

3.1 Formal version
We capture this via two axioms about 
𝑅
:

Axiom R1 (Observer‑independent reality):

𝑅
:
𝑇
→
𝑊
is defined for all 
𝑡
∈
𝑇
, and its definition does not reference agents or data:

𝑅
 is defined without dependence on 
𝐴
 or 
D
a
t
a
𝑎
.
In words: agents and data streams do not define reality; they only sample it.

Axiom R2 (Temporal totality):

∀
𝑡
∈
𝑇
:
 
𝑅
(
𝑡
)
 exists and is uniquely defined.
There is a world state at every time, regardless of observation.

Then KAD’s Assumption 2 is:

Assumption 2 (Reality is continuous / independent):  
For all times 
𝑡
∈
𝑇
, there exists a world state 
𝑅
(
𝑡
)
∈
𝑊
, and this state is defined independently of any agent’s perception or data collection.

This is basically the combination of R1 and R2.

3.2 “Proof” style argument
Here, Assumption 2 is directly encoded in R1 and R2. So the “proof” is really a definition‑level identification:

Proposition (Reality Independence):  
If R1 and R2 hold, then KAD Assumption 2 holds.

Proof:  
R2 ensures that for every 
𝑡
∈
𝑇
, there is a well‑defined world state 
𝑅
(
𝑡
)
.
R1 ensures that 
𝑅
 is defined without reference to any agent’s data or perception.
Together, they state exactly that reality exists and is defined for all times, independently of observation.
This matches the verbal content of Assumption 2. 
