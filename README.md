# Week 4 Assessment

### Setup
* Fork this repository
* You may make edits directly in github
* For the Exercise section, you will want to be logged in to [replit](https://replit.com)

## Questions (8 points possible)
1. In your own words, how would you define an ORM?

ORM is a framework that allows a programmer to connect an application and a database

2. Given the two classes for bike and owner, update the classes to include a one-to-many relationship where each bike has one owner, and each owner can have many bikes.

    ```C#
    namespace BikeApp
    {
        public class Bike
        {
            public int Id { get; set; }
            public string Type { get; set; }
            public DateTime PurchaseDate { get; set; }
            public Owner OwnedBy { get; set; }
        }
    }

    namespace BikeApp
    {
        public class Owner
        {
            public int Id { get; set; }
            public string Name { get; set; }
            public int Zipcode { get; set; }
        }
    }
    ```

3. When adding a new pizza table to our database, which of the following two commands would we run first? Why is it important to run these two line in that order?
    ```
    add-migration AddPizzaTable
    ```
    ```
    update-database
    ```
    
    You'd run the 'add-migration' one first, and then the 'update-database'. The 'add-migration' keyword creates a new class that shows the changes that have been made. 
    Using the 'update-database' keyword pushes those changes to a database.

4. For all three parts of this question, imagine that you have used Entity Framework to create a database table using the following class and context. 
    * What will the table name be?
    Bike
    
    * What will the column name(s) be?
    id, type, date
    
    * What is the name of the database you are connecting to?
    Bikes
    

    ```C#
    namespace BikeApp
    {
        public class Bike
        {
            public int Id { get; set; }
            public string Type { get; set; }
            public DateTime Date { get; set; }
        }
    }

    namespace BikeApp
    {
        public class BikeContext : DbContext
        {
            public DbSet<Bike> Bikes { get; set; }
            protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder) => optionsBuilder.UseNpgsql("Host=localhost;Username=postgres;Password=password123;Database=Bikes").UseSnakeCaseNamingConvention();
        }
    }
    ```

5. What type of data does the `Contains` LINQ method return?
    <br> a. String 
    <br> b. Integer 
    <br> c. Boolean
    
    C

## Exercise (5 points possible)

Fork the Replit below, and complete the 5 LINQ exercises.  Add a link to your forked repl here: https://replit.com/@JamesCepriano/Mod2Week4Assessment#main.cs

[https://replit.com/@launch-team/Mod2Week4Assessment](https://replit.com/@launch-team/Mod2Week4Assessment?v=1)

### Submission
* Submit a link to your forked repository in the Submission form provided in your slack channel.

## Rubric

This assessment has a total of 13 points possible.  A score of **9** or higher is a pass.

As a reminder, this assessment is for students and instructors to determine if there are any areas that need additional reinforcement!
