# portfolio-site


1. Display system date in the given format
sh
Copy
Edit
#!/bin/bash
echo "Today is $(date +"%B %d %Y")"
echo "Today is $(date +"%A")"
echo "Time is in $(date +"%I:%M:%S %p")"
2. Calculate the sum of two given numbers
sh
Copy
Edit
#!/bin/bash
read -p "Enter first number: " a
read -p "Enter second number: " b
sum=$((a + b))
echo "Sum: $sum"
3. Perform addition, subtraction, multiplication, and division
sh
Copy
Edit
#!/bin/bash
read -p "Enter first number: " a
read -p "Enter second number: " b
echo "Addition: $((a + b))"
echo "Subtraction: $((a - b))"
echo "Multiplication: $((a * b))"
echo "Division: $((a / b))"
4. Find the maximum of two numbers
sh
Copy
Edit
#!/bin/bash
read -p "Enter first number: " a
read -p "Enter second number: " b
if [ $a -gt $b ]; then
    echo "Maximum: $a"
else
    echo "Maximum: $b"
fi
5. Check whether a number is odd or even
sh
Copy
Edit
#!/bin/bash
read -p "Enter a number: " num
if (( num % 2 == 0 )); then
    echo "Even"
else
    echo "Odd"
fi
6. Check if a number is positive, negative, or zero
sh
Copy
Edit
#!/bin/bash
read -p "Enter a number: " num
if [ $num -gt 0 ]; then
    echo "Positive"
elif [ $num -lt 0 ]; then
    echo "Negative"
else
    echo "Zero"
fi
7. Calculate the sum of first N natural numbers
sh
Copy
Edit
#!/bin/bash
read -p "Enter N: " n
sum=0
for (( i=1; i<=n; i++ )); do
    sum=$((sum + i))
done
echo "Sum: $sum"
8. Find the factorial of a given number
sh
Copy
Edit
#!/bin/bash
read -p "Enter a number: " num
fact=1
for (( i=1; i<=num; i++ )); do
    fact=$((fact * i))
done
echo "Factorial: $fact"
9. Calculate sum of odd and even digits separately
sh
Copy
Edit
#!/bin/bash
read -p "Enter a number: " num
sum_odd=0
sum_even=0
while [ $num -gt 0 ]; do
    digit=$((num % 10))
    if (( digit % 2 == 0 )); then
        sum_even=$((sum_even + digit))
    else
        sum_odd=$((sum_odd + digit))
    fi
    num=$((num / 10))
done
echo "Sum of odd digits: $sum_odd"
echo "Sum of even digits: $sum_even"
10. Check if a number is prime
sh
Copy
Edit
#!/bin/bash
read -p "Enter a number: " num
if [ $num -lt 2 ]; then
    echo "Not Prime"
    exit
fi
for (( i=2; i*i<=num; i++ )); do
    if (( num % i == 0 )); then
        echo "Not Prime"
        exit
    fi
done
echo "Prime"
11. Check integer code (1 or 2)
sh
Copy
Edit
#!/bin/bash
read -p "Enter code: " code
case $code in
    1) echo "Valid code: 1";;
    2) echo "Valid code: 2";;
    *) echo "Wrong code";;
esac
12. Check integer code (1 to 4)
sh
Copy
Edit
#!/bin/bash
read -p "Enter code: " code
case $code in
    1|2|3|4) echo "Valid code: $code";;
    *) echo "Wrong code";;
esac
13. Create a menu-driven shell script for file operations
sh
Copy
Edit
#!/bin/bash
while true; do
    echo "1. Copy source file to destination"
    echo "2. Rename the specified file"
    echo "3. Print the contents of the file"
    echo "4. Change permission of file (read, write) for all users"
    echo "5. Display size of the file in bytes"
    echo "6. Exit"
    read -p "Enter your choice: " choice

    case $choice in
        1) read -p "Enter source file: " src
           read -p "Enter destination file: " dest
           cp "$src" "$dest"
           echo "File copied successfully."
           ;;
        2) read -p "Enter existing filename: " old
           read -p "Enter new filename: " new
           mv "$old" "$new"
           echo "File renamed successfully."
           ;;
        3) read -p "Enter filename to display content: " file
           cat "$file"
           ;;
        4) read -p "Enter filename to change permission: " file
           chmod 666 "$file"
           echo "Permissions changed to read & write for all users."
           ;;
        5) read -p "Enter filename to check size: " file
           size=$(stat -c %s "$file")
           echo "Size of file: $size bytes"
           ;;
        6) exit 0 ;;
        *) echo "Invalid choice!" ;;
    esac
done
14. Menu-driven script for system commands
sh
Copy
Edit
#!/bin/bash
while true; do
    echo "1. List of logged-in users"
    echo "2. Present working directory"
    echo "3. Exit"
    read -p "Enter choice: " choice

    case $choice in
        1) who ;;
        2) pwd ;;
        3) exit 0 ;;
        *) echo "Invalid choice!" ;;
    esac
done
15. Remove all files of given extensions
sh
Copy
Edit
#!/bin/bash
read -p "Enter file extension to delete (e.g., txt, log): " ext
rm *."$ext"
echo "All .$ext files deleted."
16. List files with read and write permissions for others
sh
Copy
Edit
#!/bin/bash
ls -l | awk '$1 ~ /^..w..w..w/ {print $9}'
17. Display only files in the current directory
sh
Copy
Edit
#!/bin/bash
ls -p | grep -v /
18. Display only directories in the current directory
sh
Copy
Edit
#!/bin/bash
ls -d */
19. Menu-driven program for basic commands
sh
Copy
Edit
#!/bin/bash
while true; do
    echo "1. List files (ls)"
    echo "2. Show logged-in users (who)"
    echo "3. Print working directory (pwd)"
    echo "4. Exit"
    read -p "Enter choice: " choice

    case $choice in
        1) ls ;;
        2) who ;;
        3) pwd ;;
        4) exit 0 ;;
        *) echo "Invalid choice!" ;;
    esac
done
20. Operations on "computer.lst" data file
(a) Sort the file in ascending order
sh
Copy
Edit
sort computer.lst
(b) Sort the file in descending order
sh
Copy
Edit
sort -r computer.lst
(c) Sort the file ignoring case
sh
Copy
Edit
sort -f computer.lst
(d) Remove duplicates and sort
sh
Copy
Edit
sort -u computer.lst
(e) Count the number of words
sh
Copy
Edit
wc -w computer.lst
