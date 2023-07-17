


##  In this repository we use test data from the " Food delivery service"
* I want to analyze  and calculate several important indicators using only SQL that characterize its performance
* Visualize the obtained values with the integrated Redash interface and compile the final dashboard

I will place the solution for each task in individual .txt files

***
**↓↓↓** **Let's put all the graphs from the data study on one dashboard** **↓↓↓** 

[Analysis of the delivery service indicators - part 1](http://redash.public.karpov.courses/public/dashboards/XBAhoODgM10AZrzBngylXnqy6X4IShKizJRtZqng?org_slug=default)
***

###  Part 2, where I'll calculate the Product Metrics is [here](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-part2)
***
### Database schema

![1](https://i.ibb.co/K6Dr75s/2023-01-24-214337-negate.jpg)

***
### Case Study 1

First, let's analyze how fast the audience of our service is growing, and look at the dynamics of the number of users and couriers. 

Task:

For each day presented in the user_actions and courier_actions tables, calculate the following indicators:

1. **The number of new users and the number of new couriers**.
2. **The total number of users, couriers for the current day**.

_Comparing absolute values is not very convenient. Let's calculate the dynamics of indicators in relative values._

3. **Increase in the number of new users, new couriers**.
4. **Increase  of the total number of users, total number of couriers**.


[1] [New Users and Couriers](http://redash.public.karpov.courses/embed/query/21240/visualization/32378?api_key=kwweD6rAYkwh215CzXgdZF8wmmjgW6Lus0Q0WgKK&)

[2] [Total Users and Couriers Growth](http://redash.public.karpov.courses/embed/query/21240/visualization/32379?api_key=kwweD6rAYkwh215CzXgdZF8wmmjgW6Lus0Q0WgKK&)

[3] [New Users and Couriers Change by Date, %](http://redash.public.karpov.courses/embed/query/21240/visualization/32391?api_key=kwweD6rAYkwh215CzXgdZF8wmmjgW6Lus0Q0WgKK&)

[4] [Total Users and Couriesr Crowth by Date, %](http://redash.public.karpov.courses/embed/query/21240/visualization/32392?api_key=kwweD6rAYkwh215CzXgdZF8wmmjgW6Lus0Q0WgKK&)


The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/New%20Users%20and%20Couriers.txt)

***
### Case Study 2

Now, I suggest to look at our audience from a slightly different angle - let's count not just all users, but precisely the part that makes and pays for orders in our service. At the same time let's find out what share of paying users make up of their total number.

Task:

For each day presented in the user_actions and courier_actions tables, calculate the following indicators:

1. **Number of paying users and active couriers**.
2. **The share of paying users, the share of active couriers in the total number of users for the current day**.

_Comments:_ 

We will consider those users who have placed at least one order on a given day, which was not cancelled later.

Couriers will be considered active if on a given day they took at least one order, which was delivered (probably, the next day), or delivered any order.

The total number of users/couriers for the current day is still the result of adding up the number of new users/couriers for the current day with the values of the similar indicator of all previous days. We counted this figure in the previous steps.

[1] [Paying Users and Active Couriers](http://redash.public.karpov.courses/embed/query/21276/visualization/32447?api_key=oQf3wceBc2nn3fgZOmN0WTRGkjFVo7X9YbgQutt3&)

[2] [Paying Users and Active Couriers Share, %](http://redash.public.karpov.courses/embed/query/21276/visualization/32448?api_key=oQf3wceBc2nn3fgZOmN0WTRGkjFVo7X9YbgQutt3&)

The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/Paying%20Users%20and%20Active%20Couriers.txt)

***
### Case Study 3

Let's take a deeper look at paying users, dig a little deeper, and find out how many paying users make more than one order a day. In the end, it's important for us to understand how most of our users behave-they go into the app to place just one order, or our service is so good that they are willing to use it several times a day.

Task:

For each day presented in the user_actions table, calculate the following metrics:

1. **The share of users who placed just one order that day in the total number of paying users**.
2. **The share of users who placed multiple orders that day in the total number of paying users**.

[1-2] [Single Order Users and Several Order Users Share, %](http://redash.public.karpov.courses/embed/query/21382/visualization/32604?api_key=LIvB03lm4f6BiZgPMF2piGeUPr6LSuTEpC9jnKmB&)

The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/Single%20Order%20Users%20and%20Several%20Order%20Users%20Share%2C%20%25.txt)

***
### Case Study 4

Let's continue to explore our service and calculate a few metrics related to orders.

Task:

For each day presented in the user_actions table, calculate the following indicators:

1. **Total number of orders**.
2. **The number of first orders (orders placed by users for the first time)**.
3. **The number of new user orders (orders placed by users on the same day they first used the service)**.
4. **Share of first orders in total number of orders**.
5. **The share of new users' orders in the total number of orders**.

[1-3] [Orders, First Orders and Orders from New Users](http://redash.public.karpov.courses/embed/query/21414/visualization/32725?api_key=gs5p2BHsO6S6NuReBUrAKFaKGmujfnPMzm1EXtZQ&)

[4-5] [Orders, First Orders and Orders from New Users Share, %](http://redash.public.karpov.courses/embed/query/21414/visualization/32726?api_key=gs5p2BHsO6S6NuReBUrAKFaKGmujfnPMzm1EXtZQ&)

The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/Orders%2C%20First%20Orders%20and%20Orders%20from%20New%20Users.txt)

***
### Case Study 5

Now let's try to roughly estimate the load on our couriers and find out how many orders and users on average account for each of them.

Task:

Based on the data in the user_actions, courier_actions, and orders tables, count the following for each day:

1. **The number of paying users per active courier**.
2. **The number of orders per active courier**.

[1-2] [Users and Orders per Couriers](http://redash.public.karpov.courses/embed/query/21455/visualization/32738?api_key=k1LbKkvn2dPGnlGgkxhW8KCgWpEuCS0nd0YNio8o&)

The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/Users%20and%20Orders%20per%20Couriers.txt)

***
### Case Study 6

Let's calculate another useful indicator characterizing the quality of couriers.

Task:

Based on the data in the courier_actions table for each day, calculate how many minutes, on average, it took couriers to deliver their orders.

[Average Delivery Time](http://redash.public.karpov.courses/embed/query/21462/visualization/32749?api_key=zLdKuiIyUNRvDSGUxIl5e42lHc5TF0xksCRSbv3X&)

The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/Average%20Delivery%20Time.txt)

***
### Case Study 7

And finally, let's estimate the hourly load on our service, find out during which hours users place the most orders, and at the same time analyze how the share of cancellations changes depending on the time of order placement.

Task:

Based on the data in the table orders for each hour in a day, calculate the following indicators:

1. **The number of successful (delivered) orders**.
2. **The number of cancelled orders**.
3. **The share of cancelled orders in the total number of orders (cancel rate)**.

[1-3] [Orders by Hours](http://redash.public.karpov.courses/embed/query/21534/visualization/32843?api_key=gI5QW7bRyCFYx7TqY1RgMsn4YXUgFXJJQ9on63ue&)

The solution can be found in this [file](https://github.com/IharSkalaban/Analysis-of-Food-Delivery-Service-/blob/main/Order%20by%20Hours.txt)

