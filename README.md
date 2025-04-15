def convert_temperature(value, from_unit, to_unit):
    # Convert input to Celsius first
    if from_unit == "C":
        celsius = value
    elif from_unit == "F":
        celsius = (value - 32) * 5/9
    elif from_unit == "K":
        celsius = value - 273.15
    elif from_unit == "R":
        celsius = (value - 491.67) * 5/9
    else:
        return "Invalid"

    # Convert Celsius to target unit
    if to_unit == "C":
        return celsius
    elif to_unit == "F":
        return (celsius * 9/5) + 32
    elif to_unit == "K":
        return celsius + 273.15
    elif to_unit == "R":
        return (celsius + 273.15) * 9/5
    else:
        return "Invalid output unit"

print("✮⋆˙Temperature Converterᯓᡣ𐭩")
print("Units: C = Celsius, F = Fahrenheit, K = Kelvin, R = Rankine")

from_unit = input("Convert from (C/F/K/R): ").strip().upper()
to_unit = input("Convert to (C/F/K/R): ").strip().upper()

try:
    value = float(input(f"Enter temperature in {from_unit}: "))
    result = convert_temperature(value, from_unit, to_unit)
    print(f"{value}°{from_unit} = {result:.2f}°{to_unit}")
except:
    print("Please enter a valid number.")
