# ai-coding-projects
Coding projects for university 
#K. Schueler Artificial Intelligence university projects

[Gender Wage Gap.csv](https://github.com/schueler-gthb/ai-coding-projects/files/11769778/Gender.Wage.Gap.csv)

#Bubble sort algorithm for sorting the OECD 'Gender Wage Gap' dataset

import pandas as pd
df = pd.read_csv('Gender Wage Gap.csv')
df

# Bubble Sort algorithm for double array arr according to column with index col
def bubble_sort(arr, col):
  n = len(arr)
  for i in range(1,n):
    #Last i elements are already in place
    for j in range(1, n - i):
      #Compare adjacent elements
      if float(arr[j][col]) > float(arr[j + 1][col]):
        arr[j], arr[j + 1] = arr[j + 1], arr[j]
  return arr

  import csv
file = csv.reader(open('Gender Wage Gap.csv', 'r'))
rows = [row for row in file]

sorted_rows = [', '.join(row) + '\n' for row in bubble_sort(rows, 6)]
with open('output.csv', 'w+') as f:
    f.writelines(sorted_rows)
pd.read_csv("output.csv")

#Run times artificial dataset with bubble sort with table and graph

import csv
import random
import time

def bubble_sort(dataset, column_index):
    n = len(dataset)
    for i in range(n-1):
        for j in range(n-i-1):
            try:
                value1 = float(dataset[j][column_index])
                value2 = float(dataset[j+1][column_index])
                if value1 > value2:
                    dataset[j], dataset[j+1] = dataset[j+1], dataset[j]
            except ValueError:
                continue

# Read the 'Gender Wage Gap.csv' file
data = []
with open('Gender Wage Gap.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        data.append(row)

# Remove the header row from the dataset
header = data[0]
data = data[1:]

# Shuffle the dataset randomly
random.shuffle(data)

# Select the first 5000 points from the shuffled dataset
selected_data = data[:5000]

# Measure the time it takes to run the sorting algorithm
t = time.time()
bubble_sort(selected_data, 2)  # Sort based on column index 2 (wage)
elapsed = time.time() - t

# Save the sorted dataset to a new CSV file called 'Artificial Dataset.csv'
with open('Artificial Dataset.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(header)
    writer.writerows(selected_data)

# Print the elapsed time
print('Sorting algorithm run time in seconds:', round(elapsed, 4))

import csv
import random
import time

def bubble_sort(dataset, column_index):
    n = len(dataset)
    for i in range(n-1):
        for j in range(n-i-1):
            try:
                value1 = float(dataset[j][column_index])
                value2 = float(dataset[j+1][column_index])
                if value1 > value2:
                    dataset[j], dataset[j+1] = dataset[j+1], dataset[j]
            except ValueError:
                continue

# Read the 'Gender Wage Gap.csv' file
data = []
with open('Gender Wage Gap.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        data.append(row)

# Remove the header row from the dataset
header = data[0]
data = data[1:]

# Create a list of desired numbers of datapoints
datapoints_list = [10, 100, 500, 1000, 5000]

# Loop over the different numbers of datapoints
for num_datapoints in datapoints_list:
    # Shuffle the dataset randomly
    random.shuffle(data)

    # Select the desired number of datapoints
    selected_data = data[:num_datapoints]

    # Measure the time it takes to run the sorting algorithm
    t = time.time()
    bubble_sort(selected_data, 2)  # Sort based on column index 2 (wage)
    elapsed = time.time() - t

    # Print the elapsed time for the current number of datapoints
    print(f'Sorting algorithm run time for {num_datapoints} datapoints:', round(elapsed, 4))


pip install matplotlib

import matplotlib.pyplot as plt

# Define the data
datapoints = [10, 100, 500, 1000, 5000]
runtimes = [0.0001, 0.0033, 0.0845, 0.3517, 0.6336]

# Plot the graph
plt.plot(datapoints, runtimes, marker='o', linestyle='-', color='b')

# Add labels and title
plt.xlabel('Number of Datapoints')
plt.ylabel('Run Time (seconds)')
plt.title('Bubble Sort Algorithm')

# Display the graph
plt.show()

pip install tabulate

from tabulate import tabulate

# Define the data
datapoints = [10, 100, 500, 1000, 5000]
runtimes = [0.0001, 0.0033, 0.0845, 0.3517, 0.6336]

# Create the table
table_data = []
for i in range(len(datapoints)):
    table_data.append([datapoints[i], runtimes[i]])

# Print the table
headers = ["Number of Datapoints", "Run Time (seconds)"]
print(tabulate(table_data, headers, tablefmt="grid"))

