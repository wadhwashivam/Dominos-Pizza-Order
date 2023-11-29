# Domino's Pizza Ordering System

## Introduction
This Python-based Domino's Pizza Ordering System allows users to interactively browse the menu, add items to their order, and place an order for delivery or pickup. The system uses the pizzapy library and integrates an API created by the developer @Magicjarvis.

## Getting Started

## Setup
-----

1. Install python3
2. Download this repository
3. Install the requirements of the repository `pip install -r requirements.txt`
4. Start a python3 interpreter inside of the folder called pizzapy
5. Have fun


## Description
-----------

This is a Python wrapper for the Dominos Pizza API.

It's a port of `the pizzapi node.js module <https://github.com/RIAEvangelist/node-dominos-pizza-api>`_ written by `RIAEvangelist <https://github.com/RIAEvangelist>`_.

## Quick Start
-----------

First construct a ``Customer`` object and set the customer's address:

.. code-block:: python

    customer = Customer('Barack', 'Obama', 'barack@whitehouse.gov', '2024561111', '700 Pennsylvania Avenue NW, Washington, DC, 20408')

Then, find a store that will deliver to the address.

.. code-block:: python

    my_local_dominos = StoreLocator.find_closest_store_to_customer(customer)

In order to add items to your order, you'll need the items' product codes.
To find the codes, get the menu from the store, then search for items you want to add.
You can do this by asking your ``Store`` object for its ``Menu``.

.. code-block:: python

    menu = my_local_dominos.get_menu()

Then search ``menu`` with ``menu.search``. For example, running this command:

.. code-block:: python

    menu.search(Name='Coke')

Should print this to the console:

.. code-block:: text

    20BCOKE    20oz Bottle Coke®        $1.89
    20BDCOKE   20oz Bottle Diet Coke®   $1.89
    D20BZRO    20oz Bottle Coke Zero™   $1.89
    2LDCOKE    2-Liter Diet Coke®       $2.99
    2LCOKE     2-Liter Coke®            $2.99

After you've found your items' product codes, you can create an ``Order`` object add add your items:

.. code-block:: python

    order = Order.begin_customer_order(customer, my_local_dominos)
    order.add_item('P12IPAZA') # add a 12-inch pan pizza
    order.add_item('MARINARA') # with an extra marinara cup
    order.add_item('20BCOKE')  # and a 20oz bottle of coke

You can remove items as well!

.. code-block:: python

    order.remove_item('20BCOKE')

Wrap your credit card information in a ``CreditCard``:

.. code-block:: python

    card = CreditCard('4100123422343234', '0115', '777', '90210')

And that's it! Now you can place your order.

.. code-block:: python

    order.place(card)
    my_local_dominos.place_order(order, card)


### Prerequisites
- Ensure you have Python installed on your system.
- Install the required library using the following command:
    ```
    pip install pizzapy
    ```

### Running the Application
1. Clone the repository to your local machine.
2. Navigate to the project directory.
3. Run the application using the following command:
    ```
    python app.py
    ```

## Usage

1. The application will prompt you to enter your details and search for the nearest Domino's store.
2. You can interactively search the menu and add items to your order.
3. Review your order and choose the payment method (Cash or Credit Card).
4. Confirm if you would like to place the order.

## Code Structure

- The main run file is `app.py`.
- The application utilizes the pizzapy library, and specific functionalities are encapsulated within functions like `searchMenu` and `addToOrder`.
- The user is prompted to enter details, select items, and place the order.

```python
# Insert the provided code here
```

## Credits

- This application utilizes the pizzapy library.
- The API used in this application is created by the developer @Magicjarvis.

## Acknowledgments

Thank you to the developers of pizzapy and @Magicjarvis for their contributions to this project.

Feel free to reach out to the developer for any questions or improvements!
