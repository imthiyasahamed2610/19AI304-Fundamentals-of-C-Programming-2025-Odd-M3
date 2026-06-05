# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 31/05/2026
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
```
#include <stdio.h>

int main() {
    // Step 3: Declare variables
    int num, rem, binary[32], i, k;
    
    // Step 4: Read the decimal number
    printf("Enter a decimal number: ");
    scanf("%d", &num);
    
    // Step 5: Initialize i
    i = 0;
    
    // Step 6: Repeat while num > 0
    if (num == 0) {
        printf("Binary equivalent: 0\n");
    } else {
        while (num > 0) {
            rem = num % 2;
            binary[i] = rem;
            i++;
            num = num / 2;
        }
        
        // Step 7: Display the binary digits in reverse order
        printf("Binary equivalent: ");
        for (k = i - 1; k >= 0; k--) {
            printf("%d", binary[k]);
        }
        printf("\n");
    }
    
    return 0;
}
```
# Output:
<img width="822" height="284" alt="image" src="https://github.com/user-attachments/assets/fbfe7a45-bad4-4b3c-8ae7-a58ec08b2228" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 31/05/2026
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
```
#include <stdio.h>

int main() {
    // Step 3: Declare variables
    int i, j, k, m, min, max;
    int pos[2][2];
    int matrix[10][10]; // Fixed maximum size for the matrix
    int found = 0;
    
    // Step 4: Read the order of the matrix
    printf("Enter the order of the square matrix (m): ");
    scanf("%d", &m);
    
    // Step 5: Read matrix elements
    printf("Enter the elements of the matrix:\n");
    for(i = 0; i < m; i++) {
        for(j = 0; j < m; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    
    // Step 6: Display the matrix
    printf("The Matrix is:\n");
    for(i = 0; i < m; i++) {
        for(j = 0; j < m; j++) {
            printf("%d\t", matrix[i][j]);
        }
        printf("\n");
    }
    
    // Step 7: Find the saddle point
    for(i = 0; i < m; i++) {
        // Step 7.1 & 7.2: Find minimum in row i
        min = matrix[i][0];
        pos[0][0] = i;
        pos[0][1] = 0;
        
        for(j = 1; j < m; j++) {
            if(matrix[i][j] < min) {
                min = matrix[i][j];
                pos[0][0] = i;
                pos[0][1] = j;
            }
        }
        
        // Step 7.3 & 7.4: Let j be the column of this minimum, find maximum in this column
        int min_col = pos[0][1];
        max = matrix[0][min_col];
        pos[1][0] = 0;
        pos[1][1] = min_col;
        
        // Step 7.5: Scan column
        for(k = 1; k < m; k++) {
            if(matrix[k][min_col] > max) {
                max = matrix[k][min_col];
                pos[1][0] = k;
                pos[1][1] = min_col;
            }
        }
        
        // Step 8: Check if row minimum equals column maximum and positions match
        if(min == max && pos[0][0] == pos[1][0] && pos[0][1] == pos[1][1]) {
            printf("Saddle point found at position (%d, %d) with value: %d\n", pos[0][0], pos[0][1], min);
            found = 1;
        }
    }
    
    if(!found) {
        printf("No saddle point exists in the given matrix.\n");
    }
    
    return 0;
}
```
# Output:
<img width="786" height="668" alt="image" src="https://github.com/user-attachments/assets/7fbeb258-31a6-41b3-a99f-8151b229e378" />
# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 31/05/2026
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
```
#include <stdio.h>

int main() {
    // Step 3: Declare character arrays
    char s[100], d[100];
    int len = 0, i;
    
    // Step 6: Initialize a counter j for reversed string
    int j = 0;
    
    // Step 4: Read string using format provided
    printf("Enter a string: ");
    scanf("%[^\n]s", s);
    
    // Step 5: Find the length of the string
    while (s[len] != '\0') {
        len++;
    }
    
    // Step 7: Copy characters in reverse order
    for (i = len - 1; i >= 0; i--) {
        d[j] = s[i];
        j++;
    }
    
    // Step 8: Terminate the reversed string
    d[j] = '\0';
    
    // Step 9: Print the reversed string
    printf("Reversed string: %s\n", d);
    
    return 0;
}
```
# Output:
<img width="786" height="279" alt="image" src="https://github.com/user-attachments/assets/7b8b222a-4e17-4142-9e25-45358a3f24b2" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 31/05/2026
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    // Step 3: Declare variables
    char s[100];
    int visited[256] = {0}; // Array to track counted characters
    int i, j, n, count;
    
    // Step 4: Read string
    printf("Enter a string: ");
    scanf("%[^\n]", s);
    
    // Step 5: Calculate string length
    n = strlen(s);
    
    // Step 6 & 7: Count frequency of each character
    printf("Character Frequencies:\n");
    for (i = 0; i < n; i++) {
        // If character not yet counted
        if (visited[(unsigned char)s[i]] == 0) {
            count = 0;
            
            // Loop through string to count occurrences
            for (j = 0; j < n; j++) {
                if (s[i] == s[j]) {
                    count++;
                }
            }
            
            // Print character and its count
            printf("'%c' : %d\n", s[i], count);
            
            // Mark character as counted
            visited[(unsigned char)s[i]] = 1;
        }
    }
    
    return 0;
}
```
# Output:
<img width="776" height="636" alt="image" src="https://github.com/user-attachments/assets/2446fa41-d690-4944-b385-71579b8fd560" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 31/05/2026
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    // Step 3: Declare arrays
    char str[200];
    char words[50][50]; // To store up to 50 words, max 50 chars each
    int i = 0, j = 0, k = 0, total_words = 0;
    
    // Step 4: Read input string
    printf("Enter a string: ");
    scanf("%[^\n]s", str);
    
    // Step 5: Split the string into words
    while (str[i] != '\0') {
        // If space is encountered, terminate word and move to next row
        if (str[i] == ' ') {
            words[j][k] = '\0';
            j++;
            k = 0;
        } else {
            // Copy character to current word
            words[j][k] = str[i];
            k++;
        }
        i++;
    }
    words[j][k] = '\0'; // Terminate the final word
    total_words = j + 1;
    
    // Step 6: Compare words to detect duplicates
    for (i = 0; i < total_words; i++) {
        if (words[i][0] != '\0') { // If not already marked as duplicate
            for (j = i + 1; j < total_words; j++) {
                // If a duplicate is found
                if (strcmp(words[i], words[j]) == 0) {
                    // Mark duplicate by setting first character to null
                    words[j][0] = '\0'; 
                }
            }
        }
    }
    
    // Step 7: Print all words not marked as duplicates
    printf("String with unique words: ");
    for (i = 0; i < total_words; i++) {
        if (words[i][0] != '\0') {
            printf("%s ", words[i]);
        }
    }
    printf("\n");
    
    return 0;
}
```
# Output:
<img width="793" height="327" alt="image" src="https://github.com/user-attachments/assets/6d3f3e3f-fcd2-45a4-b37c-0c2a8157ac20" />
# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

