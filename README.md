# pythonnnn
Pseudocode and fllowchart

# userID and password as key value pairs

# admin credentials is added because admin registration not present

# other login credentials will add to this dictionary

login_DB = {'admin':'pass'}

 

# this dictionary will have the medicin details

# medicin name as key and value as list having details of medicins

medicinDB = {}

 

# for stroring user id and password as global

uid = 0

upass = 0

 

#order db user id as key and med name, price, payment done in list as value

orderDB = {'cus1':['m1', 'p1', 'y'], 'cus2':['m11', 'p22','n']}

customerDB = {}

 

# main menu

while True:

   print('Online Pharmacy Management System')

   print('1. Admin')

   print('2. New Customer')

   print('3. Registered Customer')

   print('4. Exit')

   choice = 0

   # validating user input

   while True:

        choice = input('\nEnter your choice: ')

        if choice not in ['1', '2', '3', '4']:

            print('Wrong choice! Try again!')

        else:

            break

 

   # 1. admin

   if choice == '1':

        print('\nWelcome! Admin')

        while True:

            # admin menu

            print('1. Login')

            print('2. Upload Medicin details')

            print('3. View Medicins')

            print('4. Update Medicins')

            print('5. Delete Medicins')

            print('6. Search Medicins')

            print('7. View Orders')

            print('8. Search Order')

            print('9. Exit')

 

            adminChoice = 0

           

            while True:

                adminChoice = input('\nEnter your choice: ')

                if adminChoice not in ['1', '2', '3', '4', '5', '6', '7', '8', '9']:

                    print('Wrong choice! Try again!')

                else:

                    break

            # login

            if adminChoice == '1':

                uid = input('Enter user id: ')

                upass = input('Enter user pass: ')

 

                if (uid in login_DB) and (login_DB[uid] == upass):

                    print('Login successful!')

                else:

                    print('Wrong user id or password')

 

            # upload medicin details

            if adminChoice == '2':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-Upload medicin-')

                    medName = input('Enter medicin name: ')

                    expDate = input('Enter expiry date: ')

                    price = input('Enter price: ')

                    specification = input('Enter specificatios: ')

                    ls = [expDate, price, specification]

                    medicinDB[medName] = ls

                else:

                    print('Access denied! Login first!')

 

            # View medicins

            if adminChoice == '3':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-View Medicin-\n')

                   print('Name\tExpDate\tPrice\tSpecifications')

                    for i in medicinDB:

                        print(i,'\t', '\t'.join(medicinDB[i]))

                    print()

                else:

                    print('Access denied! Login first!')

 

            # update medicins

            if adminChoice == '4':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-Update Medicin-\n')

                    medName = input('Enter medicin name: ')

                    expDate = input('Enter expiry date: ')

                    price = input('Enter price: ')

                    specification = input('Enter specificatios: ')

                    ls = [expDate, price, specification]

                    medicinDB[medName] = ls

                    print('Updated successfully!\n')

                else:

                    print('Access denied! Login first!')

 

            # delete medicins

            if adminChoice == '5':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-Delete Medicin-\n')

                    medName = input('Enter medicin name: ')

                    del medicinDB[medName]

                    print('Deleted successfully!\n')

                else:

                    print('Access denied! Login first!')

 

            # search medicins

            if adminChoice == '6':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-Search Medicin-\n')

                    medName = input('Enter medicin name: ')

 

                    if medName in medicinDB:

                        print('Medicins found!\n')

                        print('Name\tExpDate\tPrice\tSpecifications')

                        print(medName,'\t', '\t'.join(medicinDB[medName]))

                    else:

                        print('Medicins NOT found!\n')

                else:

                    print('Access denied! Login first!')

 

            # View all medicins

            if adminChoice == '7':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-View all Medicins Order-\n')

                   print('CustomerName\tMedicinName\tPrice\tPaymentDone')

                    for i in orderDB:

                        print(i,'\t', '\t'.join(orderDB[i]))

                    print()

                else:

                    print('Access denied! Login first!')

 

            # Search order

            if adminChoice == '8':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-Search Orders-\n')

                   customerID = input('Enter customer id: ')

 

                    if customerID in orderDB:

                        print('Order found!\n')

                       print('CustomerName\tMedicinName\tPrice\tPaymentDone')

                        print(customerID,'\t', '\t'.join(orderDB[customerID]))

                    else:

                        print('Order NOT found!\n')

                else:

                    print('Access denied! Login first!')

 

            # exit admin menu

            if adminChoice == '9':

                break

           

   # 2. New Customer

   if choice == '2':

        print('\nWelcome! New Customer')

        while True:

            print('1. View Medicins Details')

           print('2. Customer Registration')

            print('3. Exit')

           

            customerChoice = 0

           

            while True:

                customerChoice = input('\nEnter your choice: ')

                if customerChoice not in ['1', '2', '3']:

                    print('Wrong choice! Try again!')

                else:

                    break

 

            # View Medicins Details

            if customerChoice == '1':

                print('-View all Medicins Order-\n')

               print('CustomerName\tMedicinName\tPrice')

                for i in medicinDB:

                    print(i,'\t', '\t'.join(medicinDB[i]))

                print()

 

 

            # 2. Customer Registration

            if customerChoice == '2':

                print('-Customer Registration-\n')

                name = input('Enter name: ')

                add = input('Enter address: ')

                email = input('Enter email: ')

                contact = input('Enter contact: ')

                gender = input('Enter gender: ')

                dob = input('Enter dob: ')

                uid = input('Enter user id: ')

                upass = input('Enter password: ')

                upass = input('Enter password again!: ')

 

                login_DB[uid] = upass

                customerDB[uid] = [name, add, email, contact, gender, dob]

 

            # 3. Exit

            if customerChoice == '3':

                break

 

   #3 Registered Customer

   if choice == '3':

        print('\nWelcome! Registered Customer')

        while True:

            print('1. Login')

            print('2. View all Medicins')

            print('3. Place order')

            print('4. View order')

            print('5. View personal information')

            print('6. Exit')

           

            regCustChoice = 0

           

            while True:

                regCustChoice = input('\nEnter your choice: ')

                if regCustChoice not in ['1', '2', '3', '4', '5', '6']:

                    print('Wrong choice! Try again!')

                else:

                    break

            # 1. login   

            if regCustChoice == '1': 

                uid = input('Enter user id: ')

                upass = input('Enter user pass: ')

 

                if (uid in login_DB) and (login_DB[uid] == upass):

                    print('Login successful!')

                else:

                    print('Wrong user id or password')

 

            # 2. View all Medicins

            if regCustChoice == '2':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-View Medicin-\n')

                   print('Name\tExpDate\tPrice\tSpecifications')

                    for i in medicinDB:

                        print(i,'\t', '\t'.join(medicinDB[i]))

                    print()

                else:

                    print('Access denied! Login first!')

                   

            # 3. Place order

            if regCustChoice == '3':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-Place Order -\n')

                    medName = input('Enter medicin name: ')

                    medPrice = input('Enter medicin price: ')

                    paymentDone = input('Enter y if payment done otherwise n')

                    orderDB[uid] = [medName, medPrice, paymentDone]

                    print()

                else:

                    print('Access denied! Login first!')

 

            # 4. View order 

            if regCustChoice == '4':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-View all Medicins Order-\n')

 

                   print('CustomerName\tMedicinName\tPrice\tPaymentDone')

                    for i in orderDB:

                        print(i,'\t', '\t'.join(orderDB[i]))

                    print()

                else:

                    print('Access denied! Login first!')

 

            # 5. View personal information

            if regCustChoice == '5':

                # ceking if user is logged in or not

                if uid in login_DB and login_DB[uid] == upass:

                    print('-View personal details-\n')

                   print('CustomerName\tAddress\tEmail\tContact\tGender\tDob')

                   for i in customerDB:

                        print(i,'\t', '\t'.join(customerDB[i]))

                    print()

                else:

                    print('Access denied! Login first!')

 

            # 6. exit

            if regCustChoice == '6':

                break

 

   if choice == '4':

        break

 
