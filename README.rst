
# EXP-RTL



In the mathematical field of game theory, the iterated prisoner's dilemma is a two-player, turn-based game in 
which participants can choose to cooperate with or defect against their opponents. Defections have higher 
payoffs, but carry the almost certain risk of retaliation by opposing players.

Over the years, hundreds of strategies have been developed for IPD, ranging from very simple (e.g. Tit-For-Tat, 
which simply mirrors its opponent's last play), to highly complex, involving advanced math theories and drawing 
from psychology, biology, and evolutionary studies. 

EXP-RTL ("Exponential Retaliation") is my addition to the existing pool of strategies. EXP-RTL will cooperate if 
it makes the first the move of the game, and it will continue cooperating provided its opponent does the same. 

If its opponent defects, EXP-RTL increments a _grudges variable by 1, computes the current value of _grudges 
raised to the second power, and adds the output to a _retaliations variable. It checks the value of _retaliations 
on every move and defects if it finds it greater than zero. _retaliations is decremented by 1 after each defection, 
and if it reaches zero, EXP_RTL will resume cooperating. _grudges is never decremented, so the amount of retaliation 
inflicted by EXP-RTL grows exponentionally with every defection 
it encounters.

I used the great Axelrod library, which has hundreds of IPD strategies in very accessible format, as well as 
some highly convenient tournament functions and evolutionary processes.
