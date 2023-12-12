# Call my first request to the API

The first thing to do is to have [Postman](https://www.postman.com) installed.

Once installed, create a new workspace to import the **synkron-backend.postman_collection.json** file from the following [Utils](../utils/) section.

Make sure to update the LOCAL environment so that the HOST variable points to the correct port where the API is running locally.

Then, select the Collections -> KPortal -> Auth section and select the POST - Login request.

Make the request to get a valid token, using the default credentials in the payload.

Now you can test the other collections and the different requests within the API.

Resources:

- [Postman - Importing data](https://learning.postman.com/docs/getting-started/importing-and-exporting/importing-data/)
