The problem has three components: sellers (SHFs), buyers and economic stress imposed by Soko.

In the absence of logistical costs, the market interaction between buyers and sellers becomes a very simple microeconomic supply and demand problem. The per-unit cost of production of the farmers would be some decreasing function of quantity, that we can probably find from literature. We use this curve to then to calculate the price of the product based on supply and demand (which we would also have to find from the literature).

Soko changes the picture by introducing some extra costs:

- Logistical costs
- Service charge for buyers

(The latter is a bit problematic for us, as microeconomically it is possible that the service charge will cut out of the profits of the farmers. But this is something that this exercise can actually measure to some extent.)

The logistical costs will add an interesting component to the problem. The cost of logistics is a function of the Euclidean distance between the buyer and the seller.\* Which means that the per-unit cost of the same produce will effectively differ depending on which farmer you buy from.

Considering the fact that we are considering multiple farmers and multiple buyers, spread over different geographical locations, the right approach might be an agent-based model. Alternatively, this might be able to be solved using some high-dimensional convex optimiser.

Agent-based models will also allows us to consider temporal aspects, and the annual farming cycle, and the fact that produce has an expiration date.

The advantage of an agent-based model is that we can to some extent stress-test the market. If we introduce erratic behaviour in an agent, systematically undervaluing their product, does this crash the market? We can investigate geographical effects too.

Buyers will in general order the same produce from multiple farmers at once. Do we make them pay each farmer the same price? This would fundamentally alter the price-fixing.

Within the idealisations of microeconomics, this exercise is quite doable. I don't think the results will be quantitatively predictive of reality, but I do think it will paint us a qualitative picture.

Why this exercise could be useful:

- The effect of logistical costs. Should we make the buyer or the farmer pay for it?
- The effect of the service charge. Does it drive down prices for the farmer? Is it effectively taking a cut out of the farmer's profits?
- Stress-testing
- What happens if we let farmer set their own prices, but on the buyer side we mask the bidding process (so we do the bidding for them essentially)?
- The cost incurred by Soko due to more listings being put than can be bought. Soko would buy up the produce that does not get sold.
- What happens if we restrict farmers and buyers to always put up listings some N days before pick up day?

<small> \* Does it matter whether the buyer or the seller has to pay for the logistical costs? My intuition says that the only effect is that prices will just off-load the effect, regardless of whether we make the buyer/seller pay for it. Actually, it probably does make a difference, as each farmer and buyer is spread geographically. Making the farmer/buyer pay for logistical costs would probably have an effect due to this. </small>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjU1MjA2NjU1LDk2NDk5NjQ5LC0xMTI5Mz
A4Njc4LC0yMDUzMzYwNTcwLDExMzc4ODIwMDcsMTk5NzM1ODY2
NCwxMDQ3NjUyODg0XX0=
-->