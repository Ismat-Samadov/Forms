# Forms

## Introduction

These projects will give you a chance to actually build some forms, both using nearly-pure HTML and then graduating to using the helper methods that Rails provides.

## Project: Bare metal forms and helpers

In this project, you’ll build a form the old fashioned way and then the Rails way.

### Assignment

#### Set up the Back end

1. **Build a new Rails app**:
   - Build a new Rails app (called “re-former”):
     ```bash
     rails new re-former
     ```
   - Create a new GitHub repo and connect the remote to your local git repo. Check in and commit the initial stuff.
   - Modify your README file to say something you’ll remember later.

2. **Create and migrate a User model**:
   - Create and migrate a User model with :username, :email, and :password:
     ```bash
     rails generate model User username:string email:string password:string
     rails db:migrate
     ```
   - Add validations for presence to each field in the model.
   - Create the :users resource in your routes file.

3. **Build UsersController**:
   - Write empty methods for #new and #create in your UsersController:
     ```bash
     rails generate controller Users new create
     ```
   - Create your #new view in app/views/users/new.html.erb.

4. **HTML form**:
   - Build a form for creating a new user in app/views/users/new.html.erb.

5. **Railsy forms with #form_tag**:
   - Comment out your entire HTML form.
   - Convert your <form> tag to use a #form_tag helper and all of your inputs into the proper helper tags via #*_tag methods.

6. **Railsy-er forms with #form_with**:
   - Modify your #new action in the controller to instantiate a blank User object and store it in an instance variable called @user.
   - Rebuild the form using #form_with and the @user from your controller.

7. **Editing**:
   - Update your routes and controller to handle editing an existing user.
   - Create the Edit view at app/views/users/edit.html.erb and copy/paste your form from the New view.

8. **Save to Git and GitHub**:
   - Initialize a git repository in your project folder if you haven't already:
     ```bash
     git init
     ```
   - Add all files to the staging area:
     ```bash
     git add .
     ```
   - Commit the changes:
     ```bash
     git commit -m "Initial commit"
     ```
   - Create a new repository on GitHub.
   - Push your local repository to GitHub:
     ```bash
     git remote add origin https://github.com/USERNAME/Forms.git
     git branch -M main
     git push -u origin main
     ```

## Console Usage

To interact with the application via the Rails console:

1. **Open the Rails console**:
   ```bash
   rails console
   ```

2. **Create a new user**:
   ```ruby
   user = User.new(username: "example_user", email: "user@example.com", password: "password123")
   user.save
   ```

3. **Find existing users**:
   ```ruby
   users = User.all
   ```

4. **Update user attributes**:
   ```ruby
   user = User.find_by(username: "example_user")
   user.update(email: "new_email@example.com")
   ```

5. **Delete a user**:
   ```ruby
   user = User.find_by(username: "example_user")
   user.destroy
   ```

## Additional Resources

- Rails Guides: [Form Helpers](https://guides.rubyonrails.org/form_helpers.html)