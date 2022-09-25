
# Automatization

This script was created to parse data about restaurants, attractions and shops of the selected country and
after going through a few steps, he will make media cards out of them.



## How it works
Here is the description of how this script works, by mini roadmap, but in order to understand it properly you should look at the script
and check the comments

- As a input in **main.py**  you need to point out country code(ex:274952)
- Firstly, it parse from **tripadvisor.com** all attractions and their city code
- Secondly, it gets list of restaurants from Travel advisor API
- Thirdly, it gets detailed information from API about restaurants and attractions
- Fourthly, it makes sound text for restaurants and attractions
- Fifthly, it makes media-cards for shops, restaurants and attractions. Also it makes media-cards for cities and country.
## How to run
You can run it locally. But do it if the country is very small and has few attractions. In other cases it will take very long time. Therefore use docker instead.

- Ensure you have docker and docker compose installed
- Place the project in docker container
- Open the project in terminal
- Then:
```bash
   docker compose up --build -d
```


## API that scripts use
### Travel Advisor
- **Link:** https://rapidapi.com/apidojo/api/travel-advisor/
- **Price:** 300$/month Mega Subscription
- **Limit:** The number of requests unlimited 

## Possible exceptions
#### Parsing
- Only possible exception is if tripadvisor will change location of data. In that case you should check parcer.py and make required changes. But in parsing part I do not use xpath or classname in order to prevent exceptions
#### API responses
- There can be chance that API do not have information about attraction that we are requested because the list of attractions we get from tripadvisor. Script handles it
- There can be internal server error of API which is the mistake of API. Script handles it

### DB Location
- attractions(city-> code , attraction-> location id)
- attractions_extra(final attractions) **need**
- attractions_info(detailed information of attractions)
- attractions_sound(attractions with sound)
- cities_and_countries(city code)
- cities_and_countries_info(final cities and country) **need**
- media_cards(final media-cards) **need**
- restaurants(city-> code , restaurant-> location id)
- restaurants_extra(final restaurants) ***need**
- restaurants_info(detailed information of restaurants)
- restaurants_sound(restaurants with sound)
- shops_extra(final shops) **need**

**Before implementing code do not forget to clean DB**
