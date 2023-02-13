# final-project-food-app

#Login page for admin
admin_username = input("Enter admin username:")
admin_password = input("Enter admin password:")

if admin_username == "admin" and admin_password == "admin123":
    print("Welcome Admin!")

#Create a new food item
food_id = generate_id() # Generate a unique id for the food item
name = input("Enter Food Name:")
quantity = input("Enter Quantity:")
price = input("Enter Price:")
discount = input("Enter Discount:")
stock = input("Enter Stock:")

#Save the details in the database
save_food_details(food_id, name, quantity, price, discount, stock)

print("Food item added successfully!")

#Edit food item
food_id = input("Enter Food ID:")
name = input("Enter new Food Name:")
quantity = input("Enter new Quantity:")
price = input("Enter new Price:")
discount = input("Enter new Discount:")
stock = input("Enter new Stock:")

#View all food items
all_food_items = get_all_food_items()

#Print all food items
for item in all_food_items:
    print("FoodID:", item.food_id)
    print("Name:", item.name)
    print("Quantity:", item.quantity)
    print("Price:", item.price)
    print("Discount:", item.discount)
    print("Stock:", item.stock)
    print("************************************")

#Remove food item
food_id = input("Enter Food ID:")

#Delete the food item from the database
delete_food_item(food_id)

print("Food item deleted successfully!")
