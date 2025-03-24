#global energy_charges,customer_charges,fixed_charges,dutycharges,category_name
def calculate_residential_bill(cu, pu, cat):

    units = cu - pu
    if units < 0:
        raise ValueError("Current units must be greater than previous units.")

    energy_charges = 0
    customer_charges = 0
    fixed_charges = 0
    dutycharges = 0
    category_name = ""

    if cat == 0:  # Residential Category
        if units < 50:
            energy_charges = units * 1.95
            customer_charges, fixed_charges = 40, 10
            category_name = "Residential 1"
        elif 50 <= units < 100:
            energy_charges = (50 * 1.95) + (units - 50) * 3.10
            customer_charges, fixed_charges = 70, 10
            category_name = "Residential 1"
        else:
            energy_charges = (100 * 3.40) + (units - 100) * 4.80
            customer_charges, fixed_charges = 90, 10
            category_name = "Residential 2"

    dutycharges = units * 0.06
    bill_amount = energy_charges + customer_charges + fixed_charges + dutycharges
    return units, energy_charges, customer_charges, fixed_charges, dutycharges, bill_amount, category_name
def calculate_residential_bill(cu, pu, cat):
    units = cu - pu
    if units < 0:
        raise ValueError("Current units must be greater than previous units.")

    energy_charges = 0
    customer_charges = 0
    fixed_charges = 0
    dutycharges = 0
    category_name = ""

    if cat == 0:  # Residential Category
        if units < 50:
            energy_charges = units * 1.95
            customer_charges, fixed_charges = 40, 10
            category_name = "Residential 1"
        elif 50 <= units < 100:
            energy_charges = (50 * 1.95) + (units - 50) * 3.10
            customer_charges, fixed_charges = 70, 10
            category_name = "Residential 1"
        else:
            energy_charges = (100 * 3.40) + (units - 100) * 4.80
            customer_charges, fixed_charges = 90, 10
            category_name = "Residential 2"

    dutycharges = units * 0.06
    bill_amount = energy_charges + customer_charges + fixed_charges + dutycharges
    return units, energy_charges, customer_charges, fixed_charges, dutycharges, bill_amount, category_name

# Commercial Bill Calculation
def calculate_commercial_bill(cu, pu, cat):
    units = cu - pu
    if units < 0:
        raise ValueError("Current units must be greater than previous units.")

    energy_charges = 0
    customer_charges = 0
    fixed_charges = 0
    dutycharges = 0
    category_name = ""

    if cat == 1:  # Commercial Category
        if units < 50:
            energy_charges = units * 7.0
            customer_charges, fixed_charges = 50, 60
            category_name = "Commercial 1"
        else:
            raise ValueError("Units exceed the range for Commercial 1")

    dutycharges = units * 0.06
    bill_amount = energy_charges + customer_charges + fixed_charges + dutycharges
    return units, energy_charges, customer_charges, fixed_charges, dutycharges, bill_amount, category_name
def calculate_advertisement_bill(cu, pu, cat):
    units = cu - pu
    if units < 0:
        raise ValueError("Current units must be greater than previous units.")

    energy_charges = 0
    customer_charges = 0
    fixed_charges = 0
    dutycharges = 0
    category_name = ""

    if cat == 2:  # Advertisement Category
        if units < 50:
            energy_charges = units * 5.30
            customer_charges, fixed_charges = 45, 60
            category_name = "Advertisement and Boarding 1"
        elif 50 <= units < 100:
            energy_charges = (50 * 5.30) + (units - 50) * 6.60
            customer_charges, fixed_charges = 45, 60
            category_name = "Advertisement and Boarding 2"
        elif 100 <= units < 200:
            energy_charges = (50 * 5.30) + (50 * 6.60) + (units - 100) * 7.50
            customer_charges, fixed_charges = 45, 60
            category_name = "Advertisement and Boarding 2"
        else:
            energy_charges = (50 * 5.30) + (50 * 6.60) + (100 * 7.50) + (units - 200) * 8.0
            customer_charges, fixed_charges = 45, 60
            category_name = "Advertisement and Boarding 3"

    dutycharges = units * 0.06
    bill_amount = energy_charges + customer_charges + fixed_charges + dutycharges
    return units, energy_charges, customer_charges, fixed_charges, dutycharges, bill_amount, category_name
