# Introduction #

A quick guide on how to use the model generator


# Details #

Just download and extract the archive from this website.
Or check out the source code for this project to your hard drive.

Add the path to generate\_ls\_models or generate\_ls\_models.cmd to your PATH variable. That will allow you to access it from anywhere.

Create an empty text file in your models project dir called database.yml that contains your connection configuration.
```
# on windows you can use the following connection string
sqlserver:
  database: my_database
  host: localhost
  username: some_user
  password: some_pass

# on linux or OS X you have to setup ODBC and use the following connection string
# sqlserver:
#  dsn: MyDSN
#  username: some_user
#  password: some_pass
```

The easiest way to use the model generator is from the command line by navigating to the folder that contains the project for your models and then type `generate_ls_models`

That will generate the necessary files for you and add those to that project file. The namespace for the generated models will be the name of the project file. The path where the models will be generated is the path of the project file. And the `DataContext` for Linq will be prefixed with the first part of the project file name.
This means that if your project is located in C:\projects\crazymonkey\pos\src\CrazyMonkey.Model.csproj then the datacontext will be CrazyMonkeyDataContext, the models will be generated in C:\projects\crazymonkey\pos\src\ and the namespace the models will be generated in is CrazyMonkey.Models

This is the equivalent of issuing the command:
`generate_ls_models C:\projects\crazymonkey\pos\src\CrazyMonkey.Model.csproj CrazyMonkey.Models CrazyMonkey C:\projects\crazymonkey\pos\src\`