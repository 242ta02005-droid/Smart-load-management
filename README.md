# Smart-load-management
# Smart Load Management System

MAX_POWER = 5000   # Maximum allowed power in watts

print("==============================")
print("     SMART LOAD MANAGEMENT")
print("==============================")

# Input power consumption of loads
light = float(input("Enter Light power (W): "))
fan = float(input("Enter Fan power (W): "))
ac = float(input("Enter AC power (W): "))
tv = float(input("Enter TV power (W): "))

total_power = light + fan + ac + tv

print("\nTotal Power Consumption:", total_power, "W")
print("Maximum Allowed Power:", MAX_POWER, "W")

if total_power <= MAX_POWER:
    print("\n🟢 LOAD STATUS: NORMAL")
    print("✅ All loads can remain ON")

else:
    print("\n⚠️ HIGH POWER CONSUMPTION DETECTED")

    # Load priority management
    if ac > 0:
        print("🔴 AC: Turned OFF to reduce load")
        total_power -= ac

    if total_power > MAX_POWER and tv > 0:
        print("🟡 TV: Turned OFF to reduce load")
        total_power -= tv

    print("\nNew Power Consumption:", total_power, "W")
    print("🟢 Essential loads remain ON")
