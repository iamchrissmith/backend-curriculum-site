# Feature Testing

## Capybara & Sinatra

---

# Warmup

* What are we testing so far in our Horses app?
* What aren't we testing?
* Remember your integration testing from M1? What might an integration test for a website try to test?

---

# Feature Tests

* Mimic the behavior of the user
* Shouldn't have to know about underlying code
* Based on user stories

---

# User Stories

* As a user
* When I visit the home page
* And I fill in title
* And I fill in description
* And I click submit
* Then my task is saved

---

# User Stories

* As a **user**
* When I **visit the home page**
* And I **fill in title**
* And I **fill in description**
* And I **click submit**
* Then **I see a page with my task on it**

---

# User Stories

* As a **[user/user-type]**
* When I **[action]**
* And I **[action]**
* And I **[action]**
* And I **[action]**
* Then I **[action]**

---

# Create User Stories

* Adding a Horse to HorsesApp
* Viewing only the Horses associated with a specific Jockey
* Signing up for a new account
* Logging into an account

---

# Capybara

* Test Framework
* Allows you to test any rack-based app
* Used for feature tests
* Helps you query and interact with the DOM

---

# Capybara Methods

* visit(**'path'**)
* expect(page).to have_content("**Content**")
* expect(page).to have_css("**CSS**")
* within("**CSS**") {**Expectations or Actions**}

Highlighted item are intended to change based on the actual example.

---

# In Code

```ruby
describe "When a user visits a horses show page" do
  it "they should see information about the horse" do
    horse = Horse.create(name: "Justin")

    visit "/horses/#{horse.id}"

    within "#description" do
      expect(page).to have_content("Justin")
    end
  end
end

```

---

# Setup & First Test

On your own or with a partner:

* Follow the instructions in the lesson plan to set up your first feature test
* Try to see if you can create a test and make it pass

---

# Share

---

# Launchy

* Gem that allows us to open a page in the middle of a test
* In your Gemfile: `gem 'launchy'`
* When you want to use in your test: `save_and_open_page`

---

# Forms & Buttons

* fill_in("**identifier**", with: "**content**")
* click_link("**identifier**")
* click_button("**identifier**")
* click_link_or_button("**identifier**")
* click_on("**identifier**")
* expect(current_path).to eq("**identifier**")

---

# Workshop

## Write Feature Tests For:

* The process of creating a Horse
* That all horses are displayed on the Horse index
* That a Jockey's total winnings are displayed on their page

---

# When do I write a feature test?

* Opinions vary
* To help drive development
* To ensure user stories are functioning
* To ensure user stories continue to function
* If it's important and you don't want it to break, test it

---

# Takeaways

* Feature tests mimic user behavior
* User stories help us figure out what to put in a feature test
* Capybara allows us to
    * interact with a page
    * interpret results in our tests
* Launchy helps us debug
