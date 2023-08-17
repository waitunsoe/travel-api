# Laravel Travel Api

## day-5

-   `php artisan make:command CreateUserCommand` <br>

    -   in the handle method
        -   $this->ask()
        -   $this->secret()
        -   $this->choice()
        -   $this->info()
        -   $this->error()
        -   for error -> return -1;
        -   for success -> return 0;

-   for validation in the terminal

    -   Validator::make()

-   seeding specific seeder & NO need to call from databaseseeder
    -   `php artisan db:seed --class=RoleSeeder`
-   calling seeder from databaseseeder

    -   call the seeder from databaseseeder
        -   $this->call(RoleSeeder::class);
        -   $this->call([RoleSeeder::class])
    -   `php artisan db:seed`

-   these two are the same NOT to create the other if something goes wrong!
    1. DB::begintrasaction(); DB::commit()
    2. DB::transaction(function(){});
    
-   assigning role to user
    -   $user->roles()->attach($role->id);

### installation

1. run `composer install` command on terminal or cmd.
2. copy .env.example file content into .env file then change DB_DATABASE value with your newly created database's name.
3. rename ".env.example" file into ".env", then change DB_DATABASE=yourdatabasename,DB_USERNAME=root ,
   and DB_PASSWORD=<PASSWORD> with yours.
4. `php artisan key:generate` //to generate app secret key for encryption of password.
5. `php artisan migrate` //to create tables in database.
6. `php artisan serve` //to start server at port number 8000 (http://localhost:8000).
