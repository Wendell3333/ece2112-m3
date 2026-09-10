I. Intended Learning Outcomes

At the end of this laboratory activity, the student should be able to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

II. Instructions

Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Note
book and import Pandas as pd. The dataset contains the Model column together with the vehicle
variables used in the original experiment.
• Load the CSV file into a DataFrame named cars.
• Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any
requested table or answer.
• Do not modify values in cars; create a new DataFrame or Series for each requested subset.
• Preserve the row order of the source dataset unless stated otherwise.
• Display every requested result in an executed notebook cell.
III. Programming Problems

A. POSITIONAL AND LABEL-BASED SLICING

    cars = pd.read_csv('cars.csv')

This line of code calls an external file called "cars.csv", and then it is read and converted into an array field through pd.read_csv() and stored in the "cars" array

    cars_6_to_10 = cars.iloc[6:11]

This line of code slices the cars array from index 6 to 11 and stores the result in the "cars_6_t0_10" array.

    cars_6_to_10.loc[:, ['Model', "mpg",'cyl', "hp", 'gear']]

This line of code uses a label-based slicing; it targets the specific labels to display.

B. MODEL LOOKUP

    toyata = cars.loc[cars["Model"] == "Toyota Corolla"]

This line of code uses Boolean indexing to target the exact element in the "cars" array and then store it in the "toyota" array.

    pontiac = cars.loc[cars["Model"] == "Pontiac Firebird", ['Model', 'mpg', 'hp', 'wt']]

This line of code is a Boolean indexing with a label-based slicing. This first targets the exact element found in the "cars" array, then targets the specific labels to store at the "pontiac" array.

C. MULTI-MODEL SUBSETTING

    selected_cars = cars.loc[[2,27,29], ['Model', 'mpg', 'cyl', 'hp', 'gear']].set_index('Model')

This line of code specifically targets 2, 27, and 29; the Datsun 710, the Lotus Europa, and the Ferrari Dino. this then choose specific labels for each of the elements, and then sort by "Model" label through .set_index(), and then stores it at "selected_cars" array.
