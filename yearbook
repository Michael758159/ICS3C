import math
# Author: Michael langenegger-stewart
# Date Created: 2024 November 7th
# School Yearbook Program
# This program calculates the optimal layout dimensions (rows and columns) 
# for a given number of photos to achieve the smallest perimeter, making 
# The arrangement is as compact as possible. Users can enter multiple photo 
# counts and views a summary of the best layouts at the end.
# Functions:
#   - get_valid_input(): Repeatedly prompts user input until a valid positive 
#     integer or "done" is entered.
#   - find_best_dimensions(): Calculates the layout (rows x columns) with 
#     the smallest perimeter for given photos.
#   - main(): Runs the primary program loop, handling user interaction, 
#     storage, and summary of results.


def get_valid_input():
    while True:
        user_input = input("Input a number of photos: ")
        
        # Check if the user wants to exit
        if user_input.lower() == "done":
            print("program is done.")
            return None
        
        try:
            number_of_photos = int(user_input)
            if number_of_photos >= 1:
                return number_of_photos
            else:
                print(f"{number_of_photos} is not a valid number of photos. Please enter a positive number.")
        except ValueError:
            print("Invalid input. Please enter a positive integer or 'done' to exit.")

def find_best_dimensions(n):
    best_perimeter = None
    best_dimensions = (1, n)
    
    # Iterate through possible divisors of n
    for i in range(1, int(math.sqrt(n)) + 1):
        if n % i == 0:
            rows = i
            cols = n // i
            perimeter = 2 * (rows + cols)
            
            if best_perimeter is None or perimeter < best_perimeter:
                best_perimeter = perimeter
                best_dimensions = (rows, cols)
                
    return best_dimensions, best_perimeter

def main():
    print("Welcome to the school yearbook program!")
    
    while True:
        number_of_photos = get_valid_input()
        
        if number_of_photos is None:  # If "done" was entered, exit
            break
        
        best_dimensions, best_perimeter = find_best_dimensions(number_of_photos)
        rows, cols = best_dimensions
        print(f"The best dimensions are {rows} x {cols} photos for a perimeter of {best_perimeter}.")

# Run the program
main()

