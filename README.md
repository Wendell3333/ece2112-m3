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

This line of code call an external file called "cars.csv", and then was read converted into an array filed through pd.read_csv() and stored at "cars" array

    cars_6_to_10 = cars.iloc[6:11]

This line of code positionally slice the cars array between index 6 and 11; then store this at "cars_6_t0_10" array.

    cars_6_to_10.loc[:, ['Model', "mpg",'cyl', "hp", 'gear']]

This line of code used a labed-based slicing, it target the specific labels to display.

B. MODEL LOOKUP

    toyata = cars.loc[cars["Model"] == "Toyota Corolla"]

This line of code is an boolean indexing, where is specifically target the exact element found in the "cars" array, and then this is stored at "toyota" array.

    pontiac = cars.loc[cars["Model"] == "Pontiac Firebird", ['Model', 'mpg', 'hp', 'wt']]

This line of code is an boolean indexing with a label-based slicing, this first target the exact element found in the "cars" array, then targets the specific labels to store at "pontiac" array.

C. MULTI-MODEL SUBSETTING

    selected_cars = cars.loc[[2,27,29], ['Model', 'mpg', 'cyl', 'hp', 'gear']].set_index('Model')

This line of code specifically targets 2, 27, and 29; Datsun 710, Lotus Europa, and Ferrari Dino. this then choose specifc labels for each of the elements, and then sort by "Model" label through .set_index().
