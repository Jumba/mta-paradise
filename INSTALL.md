# MTA: Paradise Installation

## MySQL configuration

### Importing the database layout
Create a new database and import the file *database_layout.sql* into it, this should contain everything required to get started.

### Configuring the server
To make your server use your MySQL database, edit your *settings.xml* to at least contain the following settings - of course, replace the example values with the MySQL data to connect to the server.

    <settings>
        <!-- MySQL Configuration -->
        <setting name="@sql.user" value="username"/>
        <setting name="@sql.password" value="password"/>
        <setting name="@sql.database" value="database"/>
        <setting name="@sql.hostname" value="localhost"/>
        <setting name="@sql.port" value="3306"/>
        
        <!-- Registration -->
        <setting name="@players.allow_registration" value="1"/><!-- Change to 0 to disable registration and show an error message -->
        <setting name="@players.registration_error_message" value="Edit this to show the user a message when registration is disabled"/>
    </settings>

## MTA Server configuration

### Obtaining the resources
To get started, clone either the [main repository](git://github.com/marcusbauer/mta-paradise.git) or your fork into *mods/deathmatch*. It should already come with all configuration files required. 

### Linux
If you are using a linux server, edit your *mods/deathmatch/mtaserver.conf* and replace

        <module src="mta_mysql.dll"/>

with

        <module src="mta_mysql.so"/>

### Windows
You need to copy the file *mods/deathmatch/modules/libmysql.dll* to your *MTA Server* directory (the one with MTA Server.exe in it)

### Ready to go!

Assuming your MySQL connection details are correctly set up, all left to do is to start the MTA server. Otherwise, the server will keep shutting down on startup, look at *mods/deathmatch/logs/server.log* for a detailed error message.
