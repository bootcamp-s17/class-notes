#Commands that elton types is hahahahaah what a joke
psql
CREATE USER icecream WITH PASSWORD 'password'; 
CREATE DATABASE icecreamdb_dev OWNER icecream;

<!-- done with psql \q to quit out -->
<!-- to login to the database as that user -->
psql icecreamdev_dev -U 'username'

<!-- creating tables in the database -->

CREATE TABLE menu_items;
 <!-- seeding the data -->

INSERT INTO 'table name' (what the table header is called) VALUES (the data for each head);

<!-- you are now done in psql -->

<!-- to load a new laravel projet -->

in the terminal type
	laravel new project_name;
<!-- then open in the prject in your editor -->
go th the env file
	DB_HOST: localhost
	DB_PORT: 5432
	DB_DATABASE: icecreamdev_dev
	DB_USERMANE: icecream
	DB_PASSWORD: 'password'
save all files

go to the terminal, make sure you are in the root of your project
<!-- now you need to start the local server	 -->
in the termian type: php artisan serve
then go to the localhost in your browser

go back to your file and go to your routes/web.php
<!-- this will define your routes -->
go to http/controllers
<!-- thise is the file where your controllers will be -->

to make models make sure you in the terminal in the root of your project directory
	php artisan make:model MenuItem
	<!-- this will show up in your http directory -->
	php artisan make:model ItemType

in your temrminal 
	php artisan tinker
	<!-- here you can trial to make different commands -->
		App\MenuItem::all();
		<!-- this will display al the date for that table -->
		App\MenuItem::find(7);
		<!-- this will find just one item with the id of 7 -->
		App\ItemType::all();
		<!-- this will display all the items in the ItemType table -->
		App\ItemType::Where('name', '=','Toppings')-> get();
		<!-- this will display the everything that is attached to the name Topping -->
in your text editor go to the ItemType model
	in the class ItemType
	{
	function menu-item(){
		return $this->hasMany('App\MenuItem');
		<!-- make sure you return, or you will not get the data that you want -->
		}
}
	<!-- this will connect ItemTypes to MenuItem -->
in your MenuItem Model
	in the class MenuItem
	{
	function item_type(){
		return $this->belongsTo('App\ItemType');

	}
}
	<!-- this will connect MenuItem to one ItemType -->

to test this go to the terminal
	php artisan tinker
		$menu = App\MenuItem::find(1);
		<!-- this will find the menu item with the id 1 and set $menu to the item -->
		$type = App\ItemType::find(1);
		<!-- this will find the menu item with the id 1 and set $type to that item -->
		$menu -> item_type()->get();
		<!-- this will get the data and it will show the linked data from the other table -->
		$type -> menu_item();
		<!-- this will return to make sure that it is connected -->
		$type -> menu_item()->get();
		<!-- this will do the same as $menu->item_type -->

go to the routes/web.php in your editor
	to define a new route 
	Route::get('menu',function(){
		return view('menu')
		<!-- to test this you can add return 'this is where menu goes' just to make sure this works -->

	})

now you have you have to make a view to connect to the route
	go to resources
	make a new file called menu.blade.php
	<!-- in this file you can add html or your file to make sure that it will work -->
	to display the data 
		@foreach (\App\ItemType::all() as $type)
		<!-- this will loop through the types that you are giving it -->
			<h2>{{$type['name']}}</h2>
		@endforeach
		<!-- this will be our main loop that show you the ItemTypes -->
	to nest to loops
		@foreach (\App\ItemType::all() as $type)
			<h2>{{$type['name']}}</h2>
			@foreach ($type->menu_items()->get() as $item)
				<h3>{{$item['name']}}</h3>
			@endforeach
		@endforeach
		<!-- this will loop through the first loop. then loop through the items that are attached to those itemtypes and  -->
now that we have a base wireframe we need to start styling it 
	go get bootstrap from getbootstrap.com copy the cdn links (all 4)
	paste them into the Menu.blade.php in the head of the file
	<!-- elton does NOT want this included becuase he sucks at it and doesnt want to feel bad
	 -->

#Refactoring for controllers
	go to the terminal
		php artisan make::controller MenuController
		<!-- this will create a controller for menu -->

now go to your routes again and change it to 
	Route::get('menu', 'MenuController@index');
	<!-- this will change the route to the controller -->

go to your app/http/controllers/MenuController
	in class menucontroller
	{

	public function index(){
			$types = \App\ItemType:all();
			return view('menu', compact('types'));
	}
}

in your blade php change
	forech to 
		@foreach ($types as $type)




















