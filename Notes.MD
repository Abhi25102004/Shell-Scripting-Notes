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