## 🔁 Before & After Code Examples

### Example 1 – Error Handling Enhancement
**Before:**
response = requests.get(url)
data = response.json()
return data

**Issue:** The program crashed during network errors or timeouts.  

**After:**
try:
response = requests.get(url)
response.raise_for_status()
data = response.json()
return data
except Exception as e:
print(f"Error fetching weather data: {e}")
return None
**Outcome:** The program now gracefully handles failed API calls without crashing.

---

### Example 2 – Fixing Blocking Matplotlib Issue
**Before:**

plt.show() ``` 
**Problem:** Main menu froze until the user closed the figure window.  

**After:**
plt.show(block=False)
plt.pause(0.001)
**Outcome:** The graph opens smoothly, and the user can continue interacting with the menu.

---

### Example 3 – Improving Visualization Clarity
**Before:**
plt.plot(days, temps)
plt.show()

**After:**
plt.plot(days, max_temps, label='Max Temp (°C)', marker='o')
plt.plot(days, min_temps, label='Min Temp (°C)', marker='o')
plt.xlabel('Date')
plt.ylabel('Temperature (°C)')
plt.legend()
plt.grid(True)
plt.show(block=False)
**Outcome:** Clearer, more professional chart with labeled axes, gridlines, and a legend.
