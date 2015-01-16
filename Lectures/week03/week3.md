#Ruby on Rails Development
##Week 3

---
##Announcements

---
#Chapter 2

----
#Agenda 
* Scaffolding
* Rest
* Resource
* Models
  * Active Record
  * Validations
* Controllers
* Views
---
##What is 'scaffolding'
* Generated by the ```scaffold``` command
* Generates code based on the attribute notation ```name:string```
* Creates model, view, controller, helper, route, migration and tests
* Has default basic code

---
##What is REST?
> Representational State Transfer 

* Simple set of Verbs that work on each Noun of an application.

--- 
##What is a 'resource'?
* Simply a controller 
* Scaffolding creates a 1 to 1 relationship to model
* Does not need to reflect a model 
* Defaults to REST actions

```
DemoApp::Application.routes.draw do
  resources :users
end
```
```
Prefix    Verb   URI Pattern                    Controller#Action
users     GET    /users(.:format)               users#index
          POST   /users(.:format)               users#create
new_user  GET    /users/new(.:format)           users#new
edit_user GET    /users/:id/edit(.:format)      users#edit
users     GET    /users/:id(.:format)           users#show
          PATCH  /users/:id(.:format)           users#update
          PUT    /users/:id(.:format)           users#update
          DELETE /users/:id(.:format)           users#destroy
```
^Maps to CRUD actions (index,show,new,create,edit,update,destroy)

---
##PUT vs PATCH
* PATCH is like PUT however PUT works on the full dataset where as PATCH only requires the delta.
* PATCH was defined in 1995 and adopted into Rails in version 4.0

---
##Sample update request
```
started PATCH "/users/1" for 50.50.89.28 at 2014-12-26 12:22:13 +0000
Processing by UsersController#update as HTML
  Parameters: {"utf8"=>"✓", "authenticity_token"=>"dWzrsueQQJPL9PxuZnM8NnQYzrtC34PpV6sbK8bd0oaxzLHlgK0224q+OVWrDF/HApdIAZGy2ywGlzQ0oywpAQ==", "user"=>{"name"=>"chris", "email"=>"cgjohnson1@madisoncollege.edu"}, "commit"=>"Update User", "id"=>"1"}
  User Load (0.2ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = ? LIMIT 1  [["id", 1]]
   (0.1ms)  begin transaction
  SQL (0.4ms)  UPDATE "users" SET "name" = ?, "updated_at" = ? WHERE "users"."id" = ?  [["name", "chris"], ["updated_at", "2014-12-26 12:22:13.298574"], ["id", 1]]
   (29.2ms)  commit transaction
Redirected to http://grandeur-blackwater-bay-69-123648.use1.nitrousbox.com:3000/users/1
Completed 302 Found in 36ms (ActiveRecord: 29.8ms)
```

---
##Modeling demo users

![inline 200%](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial/images/figures/demo_user_model.png)

--- 
##Modeling demo microposts 

![inline 200%](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial/images/figures/demo_micropost_model.png)

---
##Rake
* Ruby make
* ```$ bundle exec rake -vT```

---
#Let's take a tour

---
#Active Record Relationships

---
##Active Record Relationships
* belongs_to
* has_many
* has_many_through

---
##Validations
* Rules to prevent invalid data from being saved
* Can be conditional
* Provides error messages back to the controller
* [http://guides.rubyonrails.org/active_record_validations.html#validation-helpers](http://guides.rubyonrails.org/active_record_validations.html#validation-helpers)

---
##Rails Console
* Let's you try out code against 
* ```$ bundle exec rails console```

---
#Rails Class Inheritance Hierarchies

[https://www.railstutorial.org/book/demo_app#sec-inheritance_hierarchies](https://www.railstutorial.org/book/demo_app#sec-inheritance_hierarchies)

---
##For next week
### Ruby Koans(lab 3)
Let's take a look at them