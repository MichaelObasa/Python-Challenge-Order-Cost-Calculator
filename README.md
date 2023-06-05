# Python-Challenge-Order-Cost-Calculator
An example of a challenge that a Software Engineer can face whilst working on an E-Commerce platform and my methodology to solving it.

# The Challenge at Hand
As a junior software engineer working on an e-commerce platform, the task is to develop a feature that calculates the total cost of a customer's order. The total cost should consider product prices, discounts, and delivery fees. The platform offers a variety of products, each with a specific price.
Please note that if the initial price, the price after discount or the quantity of a product is 0, then the cost for that product should be 0 in the end, the delivery fee is not added.

# The Task
Create a function that takes in five inputs: a list of product names, a list of product quantities, a list of product prices, a discount percentage, and a delivery fee. The function should calculate the total price for each individual product in the customer's order, the operations are applied in the following order: discount first, and then the delivery fee.
If the initial price, the price after discount or the quantity of a product is 0, then the final price for that product should be 0. The result should be returned as a string, with each product's total cost displayed on a new line.

# Solution Template
class Solution:

	def run(self, product_names, quantities, prices, discount, delivery_fee):
		#
		# I will write my code below; return type and arguments should be according to the problem\'s requirements
		#
		
		
		output = calculate_total_cost(product_names, quantities, prices, discount, delivery_fee
		return output

# My Solution
    def calculate_total_cost(self, product_names, quantities, prices, discount, delivery_fee):
        output = ""

        for name, quantity, price in zip(product_names, quantities, prices):
            initial_price = quantity * price
            discounted_price = initial_price * (100 - discount) / 100
            total_cost = discounted_price + delivery_fee if discounted_price > 0 else 0
            output += f"{name}: {total_cost:.2f}\n"

        return output.strip()

    def run(self, product_names, quantities, prices, discount, delivery_fee):
        output = self.calculate_total_cost(product_names, quantities, prices, discount, delivery_fee)
        return output


# Example usage
product_names = ["Apples", "Oranges", "Bananas"]
quantities = [5, 3, 10]
prices = [1, 2, 1]
discount = 10
delivery_fee = 5

solution = Solution()
output = solution.run(product_names, quantities, prices, discount, delivery_fee)
print(output)
