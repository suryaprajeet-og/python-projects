# python-projects
My python programs.                 B.Tech CSE First year student |CMR Institute of Technology, Hyderabad|Python &amp; C++ | Aspiring Software Engineer | Exploring AI &amp; Full-Stack Development. 

#Project1: Hotel Booking!
name = input(" Enter Customer Name: ")
gender = input(" Enter Gender: ")
if gender == "Male":
		print(" Welcome Sir! ")
elif gender == "Female":
		print(" Welcome Mam! ")
else:
		print(" Welcome! ")
age = int(input(" Enter Your Age: "))
number = int(input(" Enter Number of Members: "))
while True:
	phone = input(" Enter phone Number: ")
	if len(phone) == 10:
		print(" Saved Number!")
		break
	else:
		print(" Invalid! Type Again with 10 digits! ")
room_type = ""
while True:
	choice = input(" Enter Hotel Booking or View booking or Cancellation or Review or Exit: ")
	
	if choice == "Hotel Booking":
		print(" Welcome! ")
		room_type = input(" Enter Single or Double or Deluxe: ")
		single = 1500 
		double = 3000
		deluxe = 4500
		if room_type == "Single":
			print(" It costs 1500 per day.")
			days = int(input(" Enter Number of Days "))
			special = input(" Enter special services Yes or No: ")
			if special == "Yes":
				print(" Extra cost of 500")
				extra = 500
				total = (single * days) + extra
				print(" Total cost is: ", total)
			else:
				total = single * days
				print(" Your Total is: ", total)
				print(" Transaction successful! ")
			if days >= 3:
					print(" Discount available! ")
					discount = total * 0.20
					total = total - discount
					print(" Your Discount is: ", discount)
					print(" Total cost is: ", total)
					print(" Transaction Successful! Thank you for booking! Enjoy your time here! ")
			else:
					print(" No Discount!")
					total = total
					print(" Total cost is: ", total)
					print(" Transaction Successful! Thank you for booking! Enjoy your time here! ")
				

			
		elif room_type == "Double":
			print(" It costs 3000 per day. ")
			days = int(input(" Enter number of days: "))
			special = input(" Enter special services Yes or No: ")
			if special == "Yes":
				print(" Extra cost 1000 ")
				extra = 1000
				total = (double * days) + extra
				print(" Your total is: ", total)
			else:
				total = double * days
				print(" Your Total is: ", total)
				print(" Transaction Successful!")
			if days >= 3:
					print(" Discount available! ")
					discount = total * 0.20
					total = total - discount
					print(" Your Discount is: ", discount)
					print(" Total cost is: ", total)
					print(" Transaction Successful! Thank you for booking! Enjoy your time here! ")
			else:
					print(" No Discount!")
					total = total
					print(" Total cost is: ", total)
					print(" Transaction Successful! Thank you for booking! Enjoy your time here! ")
			
		elif room_type == "Deluxe":
			print(" It costs 4500 per day.")
			days = int(input(" Enter Number of Days: "))
			special = input(" Enter special services Yes or No: ")
			if special == "Yes":
				print(" Extra cost 1500")
				extra = 1500
				total = (deluxe * days) + extra
				print(" Your Total is: ", total)
				print(" Transaction Successful!")
			else:
				total = deluxe * days
				print(" Your Total is: ", total)
				print(" Transaction Successful!")
			if days >= 3:
					print(" Discount available! ")
					discount = total * 0.20
					total = total - discount
					print(" Your Discount is: ", discount)
					print(" Total cost is: ", total)
					print(" Transaction Successful! Thank you for booking! Enjoy your time here! ")
			else:
					print(" No Discount!")
					total = total
					print(" Total cost is: ", total)
					print(" Transaction Successful! Thank you for booking! Enjoy your time here! ")
			
		else:
			print(" Invalid Room Type!")
			
	elif choice == "View booking":
			if room_type == "":
				print(" No room booking found! ")
			else:
				print(" Name: ", name)
				print(" Gender: ", gender)
				print(" Room Type: ", room_type)
				print(" Number of customers: ", number)
				print(" Living for upto ", days, "Days")
				print(" Your phone number: ", phone)
				print(" Thank you for booking! Enjoy your time with us! ")
			
			
	elif choice == "Cancellation":
			cancel = input(" Are you sure You want to Cancel your booking: ")
			if cancel == "Yes":
				room_type = ""
				print(" Cancellation successful! Thank you! visit again. ")
				
			else:
				print(" Cancellation failed! ")
				
	elif choice == "Exit":
			print(" Exit Successful! Thank you, visit again. ")
			break
			
	elif choice == "Review":
			review = (input(" Please Write your Review: "))
			while True:
				rate = int(input(" Enter on a scale of 1 to 5: "))
				
				if rate < 1 or rate > 5:
					print(" Invalid rating")
				
				elif rate <= 3:
					print(" We will make sure to Improve and give better service. Thank you for your response! ")
					break
				
				
				else:
					print(" Thank you for your response! We are Glad you Enjoyed Your Time Here! ")
					print(" Thank you for booking with us! Visit again.")
					break
					
	else:
			print(" Invalid Choice! ")
			
		
#Project2: Expense Tracker

expenses =[ { "item": "burger", "price": 180, "category": "food"} , { "item": "movie", "price": 200, "category": "entertainment"} , { "item": "book", "price": 100, "category": "studies"} ] 

def add_expense():
	item = input(" Enter item Name: ")
	while True:
		try:
			price = int(input(" Enter Price of item: "))
			print("item Price = ", price)
			break
		except:
			print(" Invalid Price! ")
	category = input(" Enter Category: ")
	new_expense = { "item": item , "price": price , "category": category } 
	expenses.append(new_expense)
	print(expenses)
	
def view_expenses():
	print(expenses)
	if expenses == []:
		print(" No expenses found")
	
def search_expense():
	while True:
		search = input(" Enter item name: ").lower()
		for expense in expenses:
			if expense["item"].lower() == search:
				print("Expense Found! ")
				print(expense)
				return 
		else:
				print(" Expense Not found! ")
				

def delete_expense():
	while True:
				search = input(" Enter item name : ")
				for expense in expenses:
					if expense["item"] == search:
						print(" Expense found! ")
						expenses.remove(expense)
						print(" Deleted successfully")
						print(expenses)
						return
				else:
						print(" Expense Not found!")
						
def total_spending():
		total = 0
		for expense in expenses:
			price = expense["price"]
			total += price
			
		print(" Total Expenses is: ", total)
		return
		
def expensive():
		highest = 0
		for expense in expenses:
			if expense["price"] > highest:
				highest = expense["price"]
		print(" Expensive expense is: ", highest)
		
def category():
		while True:
			category = input(" Enter Category of item: ")
			for expense in expenses:
				if category == expense["category"]:
					print(" Expense found! ")
					print(expense)
					return
			
		
		
def save_data():
		with open("expenses.txt" , "w") as file:
			
			for expense in expenses:
				file.write( expense["item"] + "," +  str(expense["price"]) + "," + expense["category"] + "\n" ) 
			print("Data saved successfully! ")
			
def load_data():
		expenses.clear()
		
		with open("expenses.txt" , "r" ) as file:
				for line in file:
					data = line.strip().split(",")
					new_expenses = { "item":  data[0], "price":  int(data[1]),  "category":  data[2] }
					expenses.append(new_expenses)
				print(" Data loaded successfully! ")
				

print("#" * 60)
print("                Expense Tracker            ")
print("#" * 60)
while True:
	choice = input(" Enter 1. Add Expense or 2. View Expenses or 3. Search Expense or 4. Delete Expense or 5. Total Spending or 6. Expensive or 7. Show by Category or 8. Save Data or 9. Load Data or 10. Exit: ").lower()
	
	if choice == "1":
		add_expense()
	
	elif choice == "2":
		view_expenses()
		
	elif choice == "3":
		search_expense()
		
	elif choice == "4":
		delete_expense()
		
	elif choice == "5":
		total_spending()
		
	elif choice == "6":
		expensive()
		
	elif choice == "7":
		category()
		
	elif choice == "8":
		save_data()
		
	elif choice == "9":
		load_data()
		
	elif choice == "10":
		print(" Exit Successful! ")
		break
		
	else:
		print(" Invalid choice! ")
   
	
# PROJECT 3: LIBRARY MANAGEMENT SYSTEM 

name = input(" Enter Customer name: ")
print(" Welcome to The Great Library, ", name)

library = [
    {"title": "Mother", "author": "Lakshmi", "availability": "yes"},
    {"title": "Sports", "author": "Phani", "availability": "yes"},
    {"title": "Coding", "author": "ChatGPT", "availability": "yes"},
    {"title": "Harry Potter", "author": "J.K. Rowling", "availability": "yes"}
]

def add_book():
    while True:
        title = input(" Enter Book Title: ")
        author = input(" Enter author name: ")
        availability = "yes"
        new_book = {"title": title, "author": author, "availability": availability}
        library.append(new_book)
        print(library)
        return

def view_library():
    print(library)

def search_book():
    title = input(" Enter Title of Book: ")
    for book in library:
        if book["title"] == title:
            print(book)
            break
    else:
        print(f" No Book with, {title}, Title found ")
    return

def borrow_book():
    title = input(" Enter Title of The Book: ")
    for book in library:
        if book["title"] == title:
            if book["availability"] == "yes":
                print(" Book found! ")
                print(" Book borrowed Successfully! ")
                book["availability"] = "no"
                break
            else:
                print(" Book Unavailable! ")
                break
    else:
        print(" Book not found! ")

def return_book():
    title = input(" Enter Book Title: ")
    for book in library:
        if book["title"] == title:
            if book["availability"] == "no":
                print(" Book Returned Successfully! ")
                book["availability"] = "yes"
            else:
                print(" Book not Borrowed by anyone for return! ")
            break
    else:
        print(" Book Not Found! ")
    return

def delete_book():
    title = input(" Enter book Title: ")
    for book in library:
        if book["title"] == title:
            print(" Book Found")
            print(" Book Deleted successfully")
            library.remove(book)
            break
    else:
        print(" Book not found")
    return

def total_books():
    print(len(library))

def save_data():
    with open("library.txt", "w") as file:
        for book in library:
            file.write(book["title"] + "," + book["author"] + "," + book["availability"] + "\n")
    print(" Data Saved Successfully! ")

def load_data():
    library.clear()
    with open("library.txt", "r") as file:
        for line in file:
            data = line.strip().split(",")
            new_books = {"title": data[0], "author": data[1], "availability": data[2]}
            library.append(new_books)
        print(" data loaded successfully! ")
        print(library)

def available_books():
    for book in library:
        if book["availability"] == "yes":
            print(book)
            break
    else:
        print(" No book available")
    return

while True:
    choice = input(" Enter 1. Add Book or 2. View Library or 3. Search Book or 4. Borrow Book or 5. Return Book or 6. Delete Book or 7. Total Books or 8. Save Data or 9. Load Data or 10. Available Books or 11. Exit: ")

    if choice == "1":
        add_book()

    elif choice == "2":
        view_library()

    elif choice == "3":
        search_book()

    elif choice == "4":
        borrow_book()

    elif choice == "5":
        return_book()

    elif choice == "6":
        delete_book()

    elif choice == "7":
        total_books()

    elif choice == "8":
        save_data()

    elif choice == "9":
        load_data()

    elif choice == "10":
        available_books()

    elif choice == "11":
        print(" Exit Successful! ")
        break

    else:
        print(" Invalid Option! ")
		
			
			

# PROJECT 4: ATM SYSTEM

name = input(" Enter Name: ")
print(" Hello", name)

correct_pin = 1234
attempt = 0

while attempt < 3:
    pin = int(input(" Enter PIN: "))

    if pin == correct_pin:
        print(" Welcome back!")
        break

    else:
        print(" Wrong Pin, Try Again!")
        attempt = attempt + 1

        if attempt < 3:
            attempts_left = 3 - attempt
            print(" Attempts Left:", attempts_left)

if pin == correct_pin:

    while True:

        choice = input(" Choose Check Balance or Deposit or Withdraw or Exit: ")

        if choice == "Check Balance":
            balance = int(input(" Enter Current Balance: "))
            print(" Your Balance is:", balance)
            print(" Thank You!")

        elif choice == "Deposit":

            current_balance = int(input(" Enter Current Balance: "))
            deposit = int(input(" Enter Deposit Amount: "))

            final_balance = current_balance + deposit

            print(" Final Balance:", final_balance)

        elif choice == "Withdraw":

            current_balance = int(input(" Enter Current Balance: "))
            withdraw = int(input(" Enter Withdraw Amount: "))

            if withdraw > current_balance:
                print(" Transaction Failed! Insufficient Balance!")

            else:
                final_balance = current_balance - withdraw

                print(" Transaction Successful!")
                print(" Final Balance:", final_balance)

                if final_balance < 1000:
                    print(" WARNING! Maintain Minimum Balance!")

        elif choice == "Exit":

            print(" Exit Successful!")
            print(" Thank You! Visit Again.")
            break

        else:
            print(" Invalid Choice!")

else:
    print(" Too Many Wrong Attempts!")
    print(" Card Blocked. Try Again Later.")
			
		
			

# PROJECT 5: SMART BANKING ASSISTANT 


name = input(" Enter Customer Name: ")
current_balance = int(input(" Enter current balance: "))
def welcome():
    print("Welcome ", name)
    
(welcome())

def check_balance():
    print(" Current Balance is: ", current_balance)
    
def deposit():
    print(" Current Balance is: ", current_balance)
    deposit = int(input(" Enter Deposit Amount: "))
    new = current_balance + deposit 
    print(" Your New balance is: ", new)
    
def withdraw():
    print(" Current Balance Is: ", current_balance)
    withdraw = int(input(" Enter Withdraw amount: "))
    if current_balance < withdraw:
        print(" Transaction failed Due to Insufficient Balance! ")
    else:
            final_balance = current_balance - withdraw
            
            if final_balance > 1000:
                print(" Transaction succesful! ")
            else:
                    print(" Transaction successful! ")
                    print(" WAENING! MAINTAIN MINIMUM BALANCE.")
                    
def change_pin():
    global pin
    print(" Your Current Pin is: ", pin)
    change = input(" Do you want to Change your pin, Yes or No: ")
    if change == "Yes":
        while True:
            new_pin = int(input(" Enter your New pin: "))
            confirm = int(input(" Confirm New Pin: "))
            if new_pin == confirm:
                pin = new_pin
                print(" Pin changed Successfully! ")
                break
                
            else:
                print(" Check your new pin matching Confirm new pin! ")
                
    else:
                print(" Pin Unchanged! ")
                

attempt = 0
pin = 1234
while attempt < 3:
    pin = int(input(" Enter Pin: "))
    if pin == 1234:
        print(" Login Successful! ")
        break
    else:
        if attempt < 3:
            attempt = attempt + 1
            attempts_left = 3 - attempt
            print(" Incorrect Pin! Try again.")
            print(" Attempts Left: ", attempts_left)
        else:
            print(" Login failed! Too many attrmpts. Try again after 24 hours.")
        

if pin == 1234:
                while True:
                    choice = input(" Enter Check Balance or Deposit or Withdraw or Change Pin or Exit: ")
                    
                    if choice == "check balance":
                        check_balance()
                    
                    elif choice == "deposit":
                        deposit()
                    
                    elif choice == "withdraw":
                        withdraw()
                        
                    elif choice == "change pin":
                        change_pin()
                        
                    elif choice == "exit":
                        print(" Exit Successful! Thank You.")
                        break
                        
                    else:
                        print(" Invalid Choice! ")


