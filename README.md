# KNN_Classifier
Notes from my learning on Step by step instruction for creating a Machine learning Model for Purchase Prediction on Social Media Ads

**KNN Classifier Explanation**
Imagine you’re at a park, and there are lots of kids playing. Some are playing soccer, some are playing basketball, and some are playing on the swings.
Now, let’s say you see a new kid walk into the park, and you want to guess what they might do. How would you decide?
You could look at the kids closest to the new kid. If most of the nearby kids are playing soccer, you might guess the new kid will join them. If most are on the swings, you’d guess the new kid will probably head to the swings.
This is how K-Nearest Neighbors (KNN) works! It looks at the "closest" data points (like the nearby kids) and guesses what the new data point (the new kid) is likely to do based on what its neighbors are doing.

Imagine you’re setting up a game at the park where you guess what new kids will play based on their neighbors. In this game, you have some rules or settings you can choose to make your guesses better. These settings are like the parameters in sklearn's KNN. 
    1. n_neighbors
This is like deciding how many nearby kids you’ll look at to make your guess.
        ◦ Example: Do you want to look at 3 kids close to the new kid? Or maybe 5? This number is your "K."
    2. weights
This is how much importance you give to the nearby kids when guessing.
        ◦ "uniform": You treat all the kids the same—every kid's choice counts equally.
        ◦ "distance": Closer kids are more important! Their choices matter more in your guess.
    3. algorithm
This is like choosing how to run around the park to find the nearby kids.
        ◦ "auto": Let the computer decide the best way.
        ◦ "ball_tree" or "kd_tree": These are special ways to organize the park so it’s faster to find neighbors.
        ◦ "brute": Just check every kid one by one.
    4. p
This is how you measure "closeness" between kids.
        ◦ If p=1, it’s like walking in straight lines between kids (like blocks on a grid).
        ◦ If p=2, it’s like imagining a straight shortcut between them (like flying).
    5. metric
This is the tool you use to measure distance between kids. For most parks, we just use "minkowski", which works with the p value above.

What does leaf_size do?
It controls how many kids (data points) can fit into the smallest group, or "leaf."
    • If leaf_size is small:
Each group will be tiny, so the tree will be more detailed. Finding neighbors might take longer but can be more accurate.
    • If leaf_size is large:
Each group will be bigger, so the tree will be simpler and faster to search, but it might be less precise.
Why does it matter?
    • Speed: A smaller leaf_size can slow down the search for neighbors because it has to check more groups.
    • Memory: A larger leaf_size uses less memory because the tree is simpler.
