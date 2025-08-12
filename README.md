# Time-tracker
import pytz
from datetime import datetime

# Define cities and their time zones
cities = {
    "New York": "America/New_York",
    "London": "Europe/London",
    "Tokyo": "Asia/Tokyo",
    "Sydney": "Australia/Sydney",
    "Bengaluru": "Asia/Kolkata",
    "Dubai": "Asia/Dubai",
    "San Francisco": "America/Los_Angeles"
}

def get_local_time(city, timezone_str):
    tz = pytz.timezone(timezone_str)
    local_time = datetime.now(tz)
    return local_time.strftime('%Y-%m-%d %H:%M:%S')

def display_global_times():
    print("🌐 Global Time Tracker")
    print("-" * 30)
    for city, tz_str in cities.items():
        time_str = get_local_time(city, tz_str)
        print(f"{city:15}: {time_str}")
    print("-" * 30)

if __name__ == "__main__":
    display_global_times()
