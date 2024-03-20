Steps to create Laravel8 project

composer create-project --prefer-dist laravel/laravel crud-react-laravel

After, Installation Go to the project root directory, open .env file, and set database detail as follow:
DB_CONNECTION=mysql 
DB_HOST=127.0.0.1 
DB_PORT=3306 
DB_DATABASE=<DATABASE NAME>
DB_USERNAME=<DATABASE USERNAME>
DB_PASSWORD=<DATABASE PASSWORD>


Create a Product model, migration, and controller. Run the following command for that:

php artisan make:model Category -mcr


Now, Open migration file of product from database/migration and replace code in up () function:

public function up()
{
    Schema::create('products', function (Blueprint $table) {
        $table->bigIncrements('id');
        $table->string('title');
        $table->text('description');
        $table->text('image');
        $table->timestamps();
    });
}
Migrate the database using the following command:

php artisan migrate


Now, Open Category.php model from app / Models and update code into Product.php Model:

<?php
namespace App\Models;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;
class Product extends Model {
   use HasFactory;
   protected $fillable = ['title', 'description', 'image'];
}
?>


2. Steps to Create React app: 

Create a frontend separate folder

npm install -g create-react-app 
create-react-app crud-react 
cd crud-react 
npm install axios react-bootstrap bootstrap 
npm install react-router-dom sweetalert2 --save

After the installation is completed, open up your src/app.js and import the following bootstrap core file to the top of the code:

import 'bootstrap/dist/css/bootstrap.css';

Create below files in src/components/product folder
create.component.js
edit.component.js
list.component.js


Rest can be copied from the code I have created.
