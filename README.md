# Week 7 Pod Challenge Instructions

Before you start, decide who will be the driver first. Keep an eye on the time and make sure you switch drivers at the halfway mark. Please ask for help if you are unsure how to share your code across github.

## Step 1

- Install the [corneal gem](https://github.com/thebrianemory/corneal)
```
gem install corneal
```
- Use the corneal gem to create a new Sinatra application called 'ice-cream-shop'
```
 corneal new ice-cream-shop
```

- `cd` into your new ice-cream-shop directory

## Step 2

- Go to github and create a new repository
- Connect the repository with your newly created corneal app
- Refresh the page on github to make sure it is correctly synced

## Step 3

Create migrations and set up models. You should have the following models:
- IceCream
    - has the following attributes: flavor, rating, toppings
- User (this one will only be used for the bonus)
    - has the following attributes: name, email, (password only if you have gotten to the section on passwords)

Don't forget to migrate before moving on.

## Step 4

Create some seed data. You can do this using a seeds.rb file or by starting the `rake console` and creating a few IceCream objects.

## Step 5

In your Controller, write out all 7 of the restful routes for ice creams. Try to do this on your own but if you get stuck, you can peek at the REST.png file. Add comments above each route to say what it will be used for. Don't worry yet about what happens inside of the routes, just set up the basic structure like this:
```
 # shows all the ice creams
 get '/ice_creams' do
 end
```

## Step 6

In your views folder, create the 4 view files you would need if you were implementing restful routing. Think about how we go from 7 routes to only 4 views. *Which routes do we not show views for?*

## Step 7

Add a [form](https://www.w3schools.com/html/html_forms.asp) to create new ice cream in the new.erb file. There should be a input field for each ice cream attribute and a submit button. A user should see the form if they naviagte to '/ice-creams/new' in the browser. This means you must make sure your controller action is rendering an erb file.

## Step 8

- Before submitting the form, put a `binding.pry` in the controller action where this form will send a request to. This will be a great self-check to make sure you know where your form is sending its information.

- Submit the form, and make sure it stops in the pry. Look at `params` to see the information passed through.  What kind of data type is `params`?

- In the pry, try to use the params to create a new IceCream. Once your code is working and you are able to use the params to make an IceCream, add that code into the controller action in place of the `binding.pry`

## Step 9

After creating a IceCream, redirect the user to '/ice-creams'. Add code to that controller action to do 2 things:
1. Set an instance variable `@icecreams` to be equal to all the ice creams in the IceCream class.
2. render the ice cream's ":index" view.

## Step 10

In the ice creams index.erb file, add code to do the following:
- iterate over the `@icecreams` variable
- display the flavor of each ice cream you have created. 
