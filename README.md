# Calculator_bolus_dose_for_diabetes_patients
"Bolus Dose Calculator: A useful tool for precise insulin administration. Quickly calculate the optimal dose based on blood glucose levels and carbohydrate intake. Simplifies diabetes management and promotes accurate insulin delivery. This essential medical companion is under control."

def calculator_bolus_dose(carbohydrate_amount, insulin_carb_ratio, blood_sugar_correction, insulin_sensitivity_factor):
    # calculate bolus dose for food coverage
    food_coverage_dose = carbohydrate_amount / insulin_carb_ratio

    # calculate bolus dose for high blood sugar correction
    blood_sugar_correction_dose = blood_sugar_correction / insulin_sensitivity_factor

    return food_coverage_dose, blood_sugar_correction_dose

# user usage
carbohydrate_amount = 299 # grams of carbohydrate
insulin_carb_ratio = 10  # grams of carbohydrate covered by 1 unit of insulin
blood_sugar_correction = 50  # mg/dL of blood sugar correction
insulin_sensitivity_factor = 20  # mg/dL blood sugar dropped by 1 unit of insulin

food_coverage_dose, blood_sugar_correction_dose = calculator_bolus_dose(carbohydrate_amount, insulin_carb_ratio, blood_sugar_correction, insulin_sensitivity_factor)

print("Bolus dose for food coverage:", food_coverage_dose, "units")
print("Bolus dose for high blood sugar correction:", blood_sugar_correction_dose, "units")

# Input values
carb_grams = 50  # Total grams of carbohydrates in the meal
insulin_cho_ratio = 1  # Insulin-to-carbohydrate ratio
blood_sugar_actual = 220  # Actual blood sugar level
blood_sugar_target = 120  # Target blood sugar level
correction_factor = 50  # Correction factor for high blood sugar (may vary based on individual needs)

# Calculate insulin dose for carbohydrate coverage
insulin_dose = carb_grams / insulin_cho_ratio

# Calculate high blood sugar correction
blood_sugar_correction = (blood_sugar_actual - blood_sugar_target) / correction_factor

# Round the values to two decimal places
insulin_dose = round(insulin_dose, 2)
blood_sugar_correction = round(blood_sugar_correction, 2)

# Print the results
print("Insulin dose for carbohydrate coverage: {} units".format(insulin_dose))
print("High blood sugar correction: {} units".format(blood_sugar_correction))

# Receive user input for carbohydrate coverage dose and high blood sugar correction dose
carb_dose = float(input("Enter carbohydrate coverage dose (in units):"))
correction_dose = float(input("Enter the high blood sugar correction dose (in units):"))

# Get user input for weight in pounds or kilograms
weight_unit = input("Enter weight unit (pounds or kilograms): ")
weight = float(input("Enter weight: "))

# Calculate total daily insulin dose
if weight_unit.lower() == "pounds":
    total_daily_dose = weight / 4
else:
    total_daily_dose = 0.55 * weight

# Calculate basal/background insulin dose
basal_dose = 0.5 * total_daily_dose

# Calculate carbohydrate coverage ratio
carb_coverage_ratio = 500 / total_daily_dose

# Print the results
print("Total daily insulin dose:", total_daily_dose, "units")
print("Basal/background insulin dose:", basal_dose, "units")
print("Carbohydrate coverage ratio:", carb_coverage_ratio, "grams of carbohydrate per unit of insulin")
