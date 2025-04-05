# AA_competition

The Tit-for-Tat strategy is a classic approach in game theory, especially in the context of the Iterated Prisoner's Dilemma. The key characteristics of this strategy are:

First Move:
On the first round (when no history is available), the algorithm cooperates (returns 1).

Subsequent Moves:
For every subsequent round, the algorithm simply mimics the opponent's last move:

If the opponent cooperated (played 1), the algorithm cooperates (returns 1).

If the opponent defected (played 0), the algorithm defects (returns 0).

This behavior promotes cooperation while also punishing defection. It is straightforward and has proven effective in promoting mutually beneficial outcomes when interacting with similarly cooperative strategies.







Implementation Details

Function Name: strategy

Parameters:

    my_history: A list of integers representing the algorithm's own past moves.

    opponent_history: A list of integers representing the opponent's past moves.

    rounds: An integer representing the total number of rounds, or None. The algorithm is designed to handle both cases.

Return Value:

The function returns 1 for cooperation and 0 for defection.




TEST CODE:
# test_strategy.py

def strategy(my_history, opponent_history, rounds):
    if not my_history:
        return 1
    return opponent_history[-1]

def test_strategy():
    

    # List of test cases:
    test_cases = [
        {
            "description": "Example 1 (rounds is an integer)",
            "my_history": [1, 0, 1, 1, 0],
            "opponent_history": [1, 1, 0, 1, 1],
            "rounds": 100
        },
        {
            "description": "Example 2 (rounds is None)",
            "my_history": [1, 1, 0, 0, 1, 1],
            "opponent_history": [1, 0, 1, 1, 0, 1],
            "rounds": None
        }
    ]

    for i, case in enumerate(test_cases, start=1):
        result = strategy(
            my_history=case["my_history"],
            opponent_history=case["opponent_history"],
            rounds=case["rounds"]
        )

        print(f"Test Case {i}: {case['description']}")
        print(f"  my_history       = {case['my_history']}")
        print(f"  opponent_history = {case['opponent_history']}")
        print(f"  rounds           = {case['rounds']}")
        print(f"  strategy return  = {result}\n")

if __name__ == "__main__":
    test_strategy()



