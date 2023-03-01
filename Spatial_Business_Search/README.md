# Spatial_Business_Search - MongoDB

The required task is two write two functions, which will perform some textual and spatial searching on MongoDB. Details are explained below.

### Steps:

1. Install MongoDB 2.6.11.
2. Install pymongo to act as helper interface with MongoDB.
3. Run the tester file to check everything runs and nothing fails.
4. Now, Implement the function provided in Assignment5_Interface.py to perform the operations as listed below:
    - FindBusinessBasedOnCity(cityToSearch, saveLocation1, collection)
    This function searches the ‘collection’ given to find all the business present in the city provided in ‘cityToSearch’ and save it to ‘saveLocation1’. For each business you found, you should store name Full address, city, state of business in the following format.
    Each line of the saved file will contain, Name$FullAddress$City$State. ($ is the separator and must be present)
    - FindBusinessBasedOnLocation(categoriesToSearch, myLocation, maxDistance, saveLocation2, collection)
    This function searches the ‘collection’ given to find name of all the business present in the ‘maxDistance’ from the given ‘myLocation’ that covers all the given categories (the business category needs to match at least one of the given categories) (please use the distance algorithm given below) and save them to ‘ saveLocation2’. Each line of the output file will contain the name of the business only.
        - categoriesToSearch: a list of categories need to be covered 
        - ‘myLocation’ will be given with format [“40.3”, “51.6”]. 
        - maxDistance: the search distance
        - saveLocation2: output location