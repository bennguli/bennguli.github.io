---
layout: post
title : encapsulation
---


Encapsulation can be used to hide data members and members function... Under this definition, encapsulation means that the internal representation of an object is generally hidden from view outside of the object's definition. Typically, only the object's own methods can directly inspect or manipulate its fields. Some languages like Smalltalk and Ruby only allow access via object methods, but most others (e.g. C++, C# or Java) offer the programmer a degree of control over what is hidden, typically via keywords like public and private.[4] It should be noted that the ISO C++ standard refers to protected, private and public as "access specifiers" and that they do not "hide any information". Information hiding is accomplished by furnishing a compiled version of the source code that is interfaced via a header file.

Hiding the internals of the object protects its integrity by preventing users from setting the internal data of the component into an invalid or inconsistent state. A supposed benefit of encapsulation is that it can reduce system complexity, and thus increase robustness, by allowing the developer to limit the inter-dependencies between software components[citation needed].

Almost always, there is a way to override such protection – usually via reflection API (Ruby, Java, C#, etc.), sometimes by mechanism like name mangling (Python), or special keyword usage like friend in C++.

Below is an example in C# that shows how access to a data field can be restricted through the use of a private keyword:

class Program {
	public class Account {
		private decimal accountBalance = 500.00m;

		public decimal CheckBalance() {
			return accountBalance;
		}
	}

	static void Main() {
		Account myAccount = new Account();
		decimal myBalance = myAccount.CheckBalance();

		/* This Main method can check the balance via the public
		* "CheckBalance" method provided by the "Account" class 
		* but it cannot manipulate the value of "accountBalance" */
	}
}
Below is an example in Java:

public class Employee {
    private BigDecimal salary = new BigDecimal(50000.00);
    
    public BigDecimal getSalary() {
        return salary;
    }

    public static void main() {
        Employee e = new Employee();
        BigDecimal sal = e.getSalary();
    }
}
Below is an example in PHP:

class Account {
    /**
     * How much money is currently in the account
     * @var float
     */
    private $accountBalance;

    /**
     * @param float $currentAccountBalance Initialize account to this dollar amount
     */
    public function __construct($currentAccountBalance) {
        $this->accountBalance = $currentAccountBalance;
    }

    /**
     * Add money to account
     * @param float $money Dollars to add to balance
     * @return void
     */
    public function deposit($money) {
        $this->accountBalance += $money;
    }

    /**
     * Remove money from account
     * @param float $money Dollars to subtract from balance
     * @throws Exception
     * @return void
     */
    public function withdraw($money) {
        if ($this->accountBalance < $money) {
            throw new Exception('Cannot withdraw $' . $money . ' from account as it contains $' . $this->accountBalance);
        }
        $this->accountBalance -= $money;
    }

    /**
     * Get current account balance, that takes all additions and subtractions into consideration.
     * @return float
     */
    public function getAccountBalance() {
        return $this->accountBalance;
    }
}

// Create a new object from the Account class with a starting balance of $500.00
$myAccount = new Account(500.00);

// We have clearly defined methods for adding and subtracting money from the Account
// If we didn't have a method for withdraw(), nothing would prevent us from withdrawing more money than was available in the account
$myAccount->deposit(10.24);
$myAccount->withdraw(4.45);

// Get the current balance
$accountBalance = $myAccount->getAccountBalance();
echo 'My Account Balance: $' . $accountBalance; // 505.79

// Our code forbids us from withdrawing more than we have
$myAccount->withdraw(600.00); // Exception Message: Cannot withdraw $600 from account as it contains $505.79
Encapsulation is also possible in non-object-oriented languages. In C, for example, a structure can be declared in the public API (i.e., the header file) for a set of functions that operate on an item of data containing data members that are not accessible to clients of the API:

// Header file "api.h"

struct Entity;          // Opaque structure with hidden members

// API functions that operate on 'Entity' objects
extern struct Entity *  open_entity(int id);
extern int              process_entity(struct Entity *info);
extern void             close_entity(struct Entity *info);
Clients call the API functions to allocate, operate on, and deallocate objects of an opaque data type. The contents of this type are known and accessible only to the implementation of the API functions; clients cannot directly access its contents. The source code for these functions defines the actual contents of the structure:

// Implementation file "api.c"

#include "api.h"

// Complete definition of the 'Entity' object
struct Entity {
    int     ent_id;         // ID number
    char    ent_name[20];   // Name
    ... and other members ...
};

// API function implementations
struct Entity * open_entity(int id)
{ ... }

int process_entity(struct Entity *info)
{ ... }

void close_entity(struct Entity *info)
{ ... }
Historical importance[edit]
The purpose of encapsulation (to classify) can be summarized to the following: to reduce collisions of identically named variables and to group together related methods (functions) and properties (variables) to comprise an object of class (like a family). This pattern of practice helps make source code with hundreds or thousands of lines of code more understandable and workable.

General definition[edit]
In general, encapsulation is one of the four fundamentals of OOP (object-oriented programming). Encapsulation refers to the bundling of data with the methods that operate on that data.[7] Encapsulation is used to hide the values or state of a structured data object inside a class, preventing unauthorized parties' direct access to them. Publicly accessible methods are generally provided in the class (so-called getters and setters) to access the values, and other client classes call these methods to retrieve and modify the values within the object.

This mechanism is not unique to object-oriented programming. Implementations of abstract data types, e.g. modules, offer a similar form of encapsulation. This similarity stems from the fact that both notions rely on the same mathematical fundament of an existential type
