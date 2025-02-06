# Dollar Auction Challenge

This Jupyter notebook simulates the Dollar Auction game, a game theory experiment that demonstrates how rational decision-making can lead to seemingly irrational outcomes.

## Overview

In the Dollar Auction game:
- A $1 bill is auctioned off
- Players can bid in increments of $0.05
- The highest bidder wins the dollar
- Both the highest and second-highest bidders must pay their bids
- Each player starts with $2.00

## Getting Started

### Prerequisites
- Python 3.x
- Jupyter Notebook
- pandas

Install required packages using: 
- bash
- pip install jupyter pandas

### Running the Notebook
1. Clone this repository
2. Launch Jupyter Notebook:
- bash
- jupyter notebook

3. Open `Dollar_Auction.ipynb`

## Creating Bidding Strategies

You can create new bidding strategies by defining functions that take three parameters:
- `num_players`: Total number of players in the auction
- `bid_history`: DataFrame containing previous bids
- `money`: Current amount of money available to the player

Example strategy:

```python
def my_strategy(num_players, bid_history, money):
current_bid = bid_history.iloc[-1]['bid']
if current_bid < 0.50: # Only bid if current bid is under 50 cents
return current_bid + 0.05
return False```


Return values:
- Return a float to place a bid (must be higher than current bid)
- Return `False` to pass
- Bids must be multiples of $0.05
- Bids cannot exceed player's available money

## Included Strategies

1. `cautious_carl`: Only bids minimum amount on first turn
2. `over_my_limit`: Always bids 5 cents more than current bid if affordable
3. `nervous_nelly`: Never bids

## Running Auctions

Use `run_single_auction()` with a list of player names to simulate an auction:
```python
run_single_auction(['Cautious Carl', 'nervous_nelly', 'over_my_limit'])```


The simulation will track scores across multiple auctions and display results after each game.

## License

This project is open source and available under the MIT License.
