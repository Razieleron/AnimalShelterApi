# Animal Shelter API

#### By: Jannon Sielaff

An functional API connected to an ef core database.

## Technologies Used

* C#
* Visual Studio
* .Net Framework
* SQL
* Swagger
* Postman
* EF Core

## Setup Instructions

1. Clone this repository.
2. Open your terminal (e.g., Terminal or GitBash) and navigate to this project's production directory called "AnimalShelterApi.Solution/AnimalShelterApi".
3. Create a file in /AnimalShelterApi called appsettings.json.  In this file, place the following text:

{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Port=3306;database=[your database name];uid=[your user ID];pwd=[Your password];"
  }
} 

4. In the command line, run the command "dotnet build" to compile the code. After you have compiled the code and injected all of your dependencies, you can publish the application to the internet by typing dotnet watch run.  This will allow you to query the database using an application such as Postman. There are a variety of Endpoints and Routing Methods that you can use to engage with the Api/Database.  They are as follows:

https://localhost:5001/api/animals - 

  The above Endpoint supports both Get and Post methods
    
    A Get Request to the above url will return all animals in the database
        There are ways to modify the Get Request through the following methods:  species, string, and minimumAge:
          You can edit the url to narrow your search down.  For example, if you only want to see Dogs that are over 2 years of age, the Get Request endpoint url would look something like:
              https://localhost:5001/api/animals?minimumAge=10&species=dog
    
    A Post Request to the above url will add an animal to the database
      
        The body of the post request should look like this: 
            {
              "name": "animalname",
              "species": "animalspecies",
              "age": "animalage"
            }
          ** NOTE: do not add an "animalId" parameter to the body of your post request, and this parameter is automatically generated based on the Database's Settings



  https://localhost:5001/api/animals/{id}

    The above Endpoint supports Get, Put, and Delete Methods.  In your own url, instead of {id}, enter the number that corresponds to the animalId of the animal you wish to edit.

      A Get Request to that url will return the animalId, name, species, and age of the animal
      
      A Put Request will allow you to update/edit any of the information in the animal object.  Please note that according to the HTTP specification, a PUT request requires the client to send the entire updated entity, not just the changes.  So if you wanted to change just the name of the Animal, you would need to include the animalId, the species and the age in the body

        The body of the Put request should look like this:
            {
              "animalId": "animalId",
              "name": "animalname",
              "species": "animalspecies",
              "age": "animalage"
            }

      A Delete Request to that URL will allow you to delete the animal with that animalId from the database.  
      
      ***NOTE***
        SENDING A DELETE REQUEST TO THE ENDPOINT WILL DELETE THE ANIMAL THAT HAS THE animalId THAT IS INDICATED IN THE URL.  PLEASE BE CAREFUL WHEN DELETING DATABASE ENTRIES.
      ***/NOTE***



## Known Bugs

* NA

## License

MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

* Copyright (c) _2023_ _Jannon Sielaff_
