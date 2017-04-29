#### Game Theory and Iterated Prisoner's Dilemma in Python

---

#### This comic brought me into Game Theory.

![IMAGE](https://upload.wikimedia.org/wikipedia/en/8/84/Liar_Game_vol01.jpg)

---

#### What is Game Theory?

Study Conflicts and Cooperation between various entities though Mathematical Models.

---

#### Let's Play!!

Let's play a small game to understand a bit on Game Theory- Guess 2/3rd of average.

The aim of the game is to guess the 2/3rd of the average of your guesses.

Numbers are restricted between 0 to 100, both inclusive.

---

#### Prisoner's Dilemma

- Started out as an idea at RAND Corporation.
- Formalized later by  Albert W. Tucker as a game with prison sentence rewards.

---

#### Scenario

- Two members of a criminal organization A and B are captured and put in incarceration. Both the menbers cannot communicate with each other.
- The Prosecutor doesn't have evidence and decides to give each person a bargain- betray your friend or cooperate with your friend by going silent.

---

The offer is:
- If A and B betray each other, both get imprisonment for three years.
- If A betrays and B is silent(or vice versa),  A is free and B will serve 5 years in prison.
- If both remain silent, Both serve one year in prison.

---
$$ J(\theta_0,\theta_1) = \sum_i^m  $$
---
#### Iterated Prisoner's Dilemma

1. Started out as Robert Axelrod as a student in 1962.
2. [Axelrod1980](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.665.7955&rep=rep1&type=pdf): 15 strategies
3. [Axelrod1980b](http://journals.sagepub.com/doi/abs/10.1177/002200278002400301): 65 strategies

---

### IPD in Python

![IMAGE](http://vknight.org/Talks/2017-02-13-The-Axelrod-library/static/axelrod-tweet.png)

... Now present as [Axelrod-Python/Axelrod](https://github.com/Axelrod-Python/Axelrod).

---

### Basic Strategy for IPD

```python
class TitForTat(Player):
    """A player starts by cooperating and then mimics previous move by opponent."""

    name = 'Tit For Tat'
    classifier = {
        'memory_depth': 1,  # Four-Vector = (1.,0.,1.,0.)
        'stochastic': False,
        'inspects_source': False,
        'manipulates_source': False,
        'manipulates_state': False
    }

    @staticmethod
    def strategy(opponent):
        return 'D' if opponent.history[-1:] == ['D'] else 'C'
```
---

#### Demo time!

---

The Axelrod library

Greet us at [Gitter!!](https://gitter.im/Axelrod-Python/Axelrod)

Docs- [axelrod.readthedocs.io](axelrod.readthedocs.io)

---
