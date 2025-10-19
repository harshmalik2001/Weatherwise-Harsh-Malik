## ⚙️ Six-Step Methodology Documentation

**Component:** `get_weather_data(location, forecast_days=3)`

### Step 1 – Planning
Defined the goal to retrieve accurate weather data by location using a free, accessible API. Decided on **wttr.in** for simplicity and JSON support without requiring an API key.

### Step 2 – Research
Investigated how `wttr.in` structures JSON responses and learned to append `?format=j1` to request data. Reviewed Python’s `requests` library for handling HTTP status codes.

### Step 3 – Design
Outlined the logic in pseudocode:
- Build a URL using the location string.  
- Send a GET request using `requests.get()`.  
- Parse the JSON response.  
- Include exception handling for connection errors.  
- Trim results to a 3-day forecast.

### Step 4 – Implementation
Implemented the code:
def get_weather_data(location, forecast_days=3):
    
    url = f"https://wttr.in/{location}?format=j1"
    try:
        response = requests.get(url)
        response.raise_for_status()
        data = response.json()
        data['weather'] = data['weather'][:forecast_days]
        return data
    except Exception as e:
        print(f"Error fetching weather data: {e}")
        return None
### Step 5 – Testing
Tested the function with multiple cities (`Perth`, `Sydney`). Simulated network failures using mock tests. Observed correct handling of valid and invalid inputs without program crashes.

### Step 6 – Improvement
Enhanced with user-friendly messages and integrated it with visualizations for practical utility. Added API call limitations (max 3 days) to prevent misuse.

---
