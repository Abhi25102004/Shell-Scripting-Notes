# Question Shell Script

### Peter‟s basic salary is input through the keyboard. His dearness allowance is 40% of his basic salary, and house rent allowance is 18% of the basic salary. Write a script to calculate his gross salary.

```bash
#!/bin/sh

echo "Enter the salary: \c"
read salary

echo "Gross Salary : $(echo "$salary+($salary*0.4)+($salary*0.18)"|bc)"
```

### The distance between two cities (in km.) is input through the keyboard. Write a script to convert and print this distance in meters, feet, inches and centimeters.

```bash
#!/bin/sh

echo "Enter distance (Km) : \c"
read distance

echo "$distance km = $(echo "$distance*1000"|bc) m"
echo "$distance km = $(echo "$distance*3280.84"|bc) feet"
echo "$distance km = $(echo "$distance*39370.1"|bc) inch"
echo "$distance km = $(echo "$distance*100000"|bc) cm"
```

### The length and breadth of a rectangle and radius of a circle are input through the keyboard. Write a script to calculate the area and perimeter of the rectangle as well as the area and circumference of the circle

```bash
#!/bin/sh

echo "Enter the length of the rectangle: \c"
read length

echo "Enter the breadth of the rectangle: \c"
read breadth

echo "Enter the radius of the circle: \c"
read radius

echo "Area of the rectangle is $(echo "$length*$breadth"|bc)"
echo "Perimeter of the rectangle is $(echo "2*($length+$breadth)"|bc)"
echo "Area of the circle is $(echo "3.14*$radius*$radius"|bc)"
echo "Circumference of the circle is $(echo "2*3.14*$radius"|bc)"
```

### If a five digit number is input through the keyboard, write a script to calculate the sum of its digits.

```bash
#!/bin/sh

echo "Enter a five digit number: \c"
read number

sum=0

if [ $number -ge 10000 -a $number -le 99999 ]
then
  while [ $number -ne 0 ]
  do
    remainder=`expr $number % 10`
    number=`expr $number / 10`
    sum=`expr $remainder + $sum`
  done
  echo "Sum of five digits are $sum"
else
  echo "Entered number was not of five digits"
fi
```

### In a company, an employee is paid as follows: If his basic salary is less than Rs. 5000, then HRA = 10% of basic salary and DA = 90% of basic. If his salary is either equal or above Rs. 5000, then HRA = Rs. 900 and DA = 98% of basic salary. If the employee‟s salary is input through the keyboard, write a script to find his gross salary.

```bash
#!/bin/sh

echo "Enter the salary of the employee: \c"
read salary

if [ $salary -lt 5000 ]
then
  echo "Gross salary of the employee is $(echo "$salary+($salary*0.1)+($salary*0.9)"|bc)"
elif [ $salary -ge 5000 ]
then
  echo "Gross salary of the employee is $(echo "$salary+900+($salary*0.98)"|bc)"
fi
```

### Write a script that will accept a filename from the keyboard and determine whether the file exists. If the file exists then is contents will be displayed else an error message will be displayed.

```bash
#!/bin/sh

echo "Enter the name of the file : \c"
read file

fileName=`ls|grep $file`

if [ -z $fileName ]
then
  echo "File does not exists"
elif [ -e $fileName ]
then
  echo "File exists"
  echo "The contents of the file is"
  cat $fileName
fi
```
