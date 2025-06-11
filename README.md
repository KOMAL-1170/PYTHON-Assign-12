import random
import time
import matplotlib.pyplot as plt

# Define the sizes of the lists
sizes = [5000, 10000, 15000, 20000, 25000]
times = []

# Measure time taken to sort lists of different sizes
for size in sizes:
    numbers = [random.randint(1, 1000000) for _ in range(size)]
    
    start_time = time.time()
    sorted_numbers = sorted(numbers)
    end_time = time.time()

    elapsed_time = end_time - start_time
    times.append(elapsed_time)
    print(f"Sorted {size} elements in {elapsed_time:.4f} seconds")

# Plotting the graph
plt.figure(figsize=(8, 5))
plt.plot(sizes, times, marker='o', linestyle='-', color='blue')
plt.title('List Size vs Time Taken to Sort')
plt.xlabel('Number of Elements in List')
plt.ylabel('Time Taken (seconds)')
plt.grid(True)
plt.tight_layout()
plt.show()
