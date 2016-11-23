# Rails

### Create
```
t = Tweet.new
t.status = " .... "
t.save
```

### Read
```
Tweet.find(3)
```

### Update
```
t = Tweet.find(4)
t.status = " ..... "
t.save
```

### Delete
```
Tweet.find(3).destroy
```

#### Create = New + Save
```
Tweet.create(status: "...", time: "...")
# id is created automatically. don't need to .save
```

### Read
```
.find(2, 3, 6)
.first
.last
.all
.count
.order(:key)
.limit(num)
.where(key: value)
```

#### Update multiple attributes at once
```
t = Tweet.find(2)
t.attributes = {
    key1: "value1"
    key2: "value2"}
t.save

t = Tweet.find(2)
t.update(
    key1: value1,
    key2: value2)
```

## Models
Get data out of database
```
In app/models/tweet.rb:

class Tweet < ActiveRecord::Base

< means inherits from
ActiveRecord maps class to the table "tweets"
```

### Validation
```
validates :status, presence: true, length: {minimum: 3}

presence T/F
numericality T/F
uniqueness T/F
confirmation T/F
acceptance T/F
length {minimum: , maximum: }
format {with: /.*/}
inclusion
exclusion
```

### Relationships
```
class Zombie < ActiveRecord::Base
    has_many :tweets
end

class Tweet < ActiveRecord::Base
    belongs_to :zombie
end

a = Zombie.find(1)
t = Tweet.create(status: "...", zombie: a)
```

## Views
Displays data  
Embedded Ruby within HTML  
```
Ruby code goes within <% ... %>  
Print result within <%= ... %>  

Create a link to user
<%= link_to text_to_show, code %>
<%= link_to tweet.user.name, tweet.user%>

    ACTION            CODE
List all tweets   tweets_path
New tweet form    new_tweet_path
Show tweet        tweet
Edit tweet        edit_tweet_path(tweet)
Delete tweet      tweet, :method => :delete
```

## Controller
Process & respond to events.  
Modifies models and views.  
In /app/controllers/tweets_controller.rb
```
class TweetsController < ApplicationController
    ...
end

If there's /app/views/tweets/show.html.erb,
add a def show (action)

Use instance variables (@tweet) in controller & views

Can also do render action: 'name' to tie action to diff view

def show
    @tweet = Tweet.find(params[:id])
    render action: 'status'

# now ties to /app/views/tweets/status.html.erb
```
Strong parameters - for multiple attributes  
```
require(:tweet)  - param key required
permit(:status)  - attribute to be set

@tweet = Tweet.create(params.require(:tweet).permit(:status))
```
#### Common controller actions
```
index
show
new
edit
create
update
destroy
```
### Authorization
session = per-user hash  
flash[:notice] = send message to user
redirect <path> = redirect request
```
def edit
    @tweet = Tweet.find(params[:id])
    if session[:user_id] != @tweet.user_id
        flash[:notice] = "Sorry ... "
        redirect_to(tweets_ath)

# in /app/views/layouts/application.html.erb, add

<% if flash[:notice] %>
    <div id="notice">
        <%= flash[:notice]%>
    </div>
<% end %>       # above <% =yield %>
```
## Routes
In config/routes.rb  
```
Twitter::Application.routes.draw do
    resources :tweets
end

Defines a few routes:
tweets_path            def index      /tweets
tweet                  def show       /tweets/<id>
new_tweet_path         def new        /tweets/new
edit_tweet_path(tweet) def edit       /tweets/<id>/edit
```

### Custom Routes
Need Controller name, Action name  
```
get '/new_tweet' => 'tweets#new'
# now .../new_tweet renders /tweets/new
```
#### Named Route
```
get '/all/' => 'tweets#index', as: 'all_tweets'

<% link_to "All Tweets", all_tweets_path %>
```
#### Redirecting
```
get '/all' => redirect('/tweets')
```
#### Root Route
```
root to: "tweets#index"

# its code is root_path
```

