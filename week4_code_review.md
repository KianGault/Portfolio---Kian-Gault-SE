# Code review

## Code Review example 

``` 
class Car
{
  public string model;

  // Class constructor
  public Car()
  {
    model = "Mustang"; // Set the initial value for model
  }

  static void Main(string[] args)
  {
    Car Ford = new Car();
    Console.WriteLine(Ford.model);
  }
}
```

## Analyse of the code 

The code seems clean at first sight but once looking a bit deeper there is a few redudant issues here. 

First: The first thing i noticed was everything was public (Line 3). This isn't a big issue since the code is small 
but it's still bad practice to have everything public when it should be encapsulated. 

Second: Following the KISS principle "Keep it simple" we can see the use of a constructor to set the string variable is 
actually not needed at all(Line 6-9). We could simply set the model variable the "Mustang" value when the variable is created. 
From this we could remove the constructor and reduce complexity. 

Third: In this code snippet we can see the use of short comments(Line 5, Line 8). They aren't bad comments but they are 
also unncessary in this example. The need to tell the reviewer that this is a class conctructor or this is us setting the 
model variable a value is not needed because programmers can easily tell what a constructor is or what a equals syntax does. 

Fourth: The naming of variables/instances are confusing when looking at just the code snippet as the instance is called "Ford"
so it's unclear if all the car types are ford make. Also the instance name is capitalised which is bad practice as naming should 
be camel casing. 

## Code changed 
```
class Car
{
  private string model = "Mustang"

  public string Model 
  {
    get { return model; }
    set { model = value; }
  }

  static void Main(string[] args)
  {
    Car carModel = new Car();
    Console.WriteLine(carModel.Model);
  }

}
```

## Code Changes

The first change i made was making the variable "model" private. This follows the OOP principle of keeping encapsulation. To still
make this accessible to instances of the class i create a new property that gives public access to instances. 
The second change i made was removing the constructor from the code. This wasn't needed as we could just set the model type during 
the initalising of the variable itself. The constructor would only be needed if the variable value was changed during the start-up. 
I also removed any comments in the code as the code is cleanly written so comments aren't needed. To make sure this was the case 
i also renamed some names in the code like the instance type used to be "Ford" and now it is simply carModel. 

I believe my changes made this snippet of code more clear and concise. The task of the code is clear and unneeded complexity was 
removed. I also added good coding practices to the code like encapsulation and correct naming of variables. 
I followed the YAGNI software engineering principle in removing the constructor from the code because we simply did not need it 
to complete the task and it added more complexity to the simple task. 


