# Inpursuit Backend

This repo is to hold the calls and triggers for inpursuit.

## Links to access database

#### To access the user table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-user

#### To access the pursuits table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-pursuits

#### To access the posts table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-posts

#### To access the chat table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-chat

#### To access the chat detail table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-chat-detail

#### To access the pursuits follows table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-pursuit-follow

#### To access the interests table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-interest

#### To access the user interests table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-user-interest

#### To access the saved posts table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-posts-saved

#### To access the posts comments table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-posts-comments

#### To access the posts collaboration table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-posts-collaboration

#### To access the collaboration engagements table use:

https://arcane-mesa-59373.herokuapp.com/get-mock-collaboration-engagements


## Home.js

#### My Pursuits

The my pursuits array should display all pursuits owned or followed by the logged in user. 

```

{
    "rowLabel": "My Pursuits",
    "posts": [{
        "thumbnailUrl": "https://thumbnailUrl.com",
        "userId": "123abc",
        "userPhoto": "https://userPhoto.com",
        "postId": "Post123",
        "description": "Test 123",
        "timestamp": "12324353",
        "is_public": 0
    }]
} 
```
#### Pursuits You May Like

The pursuits you may like array should return a join from the users selected interestId's and the interestId of the post. 

``` 

{
    "rowLabel": "Pursuits You May Like",
    "posts": [{
        "thumbnailUrl": "https://thumbnailUrl.com",
        "userId": "123abc",
        "userPhoto": "https://userPhoto.com",
        "username": "Test",
        "postId": "Post123",
        "timestamp": "12324353",
        "description": "Test 123",
        "is_public": 0
    }]
}

```

#### Challenges 

The challenges array should return a set of post that has been marked as challenges.

```

{
    "rowLabel": "Challenges",
    "posts": [{
        "thumbnailUrl": "https://thumbnailUrl.com",
        "userId": "123abc",
        "userPhoto": "https://userPhoto.com",
        "username": "Test",
        "postId": "Post123",
        "description": "Test 123",
        "timestamp": "12324353",
        "is_public": 0
    }]
} 

```
#### Users

This should be a return of other profiles. 

```

"users": [{
    "rowLabel": "People",
    "profiles": [{
        "username": "Test",
        "userId": "Test123",
        "userPhoto": "https://thumbnailUrl.com",
        "fullname": "Test"
    }]
}]

```
#### Remaining Arrays

The remaining arrays should be ordered by category (first by interests that the user selected then by interests that the user has not selected). 

```

{
    "rowLabel": "Animals",
    "posts": [{
        "thumbnailUrl": "https://thumbnailUrl.com",
        "userId": "123abc",
        "userPhoto": "https://userPhoto.com",
        "username": "Test",
        "postId": "Post123",
        "description": "Test 123",
        "timestamp": "12324353",
        "is_principle": 0,
        "is_step": 0,
        "is_public": 0
    }]
}

```
## Home-Detail.js

#### Days 

The days array should be a return of post separated by the last 24 hours i.e days. 

```
"rowLabel": "Day 1",
"posts": [{
    "thumbnailUrl": "https://thumbnailUrl.com",
    "description": "Test 123",
    "postId": "Post123",
    "is_step": 0,
    "is_principle": 0,
    "is_challenge": 1,
    "has_viewed": 0
}, {
    "thumbnailUrl": "https://thumbnailUrl.com",
    "description": "Test 123",
    "postId": "Post123",
    "is_step": 0,
    "is_principle": 0,
    "is_challenge": 1,
    "has_viewed": 0
}, {
    "thumbnailUrl": "https://thumbnailUrl.com",
    "description": "Test 123",
    "postId": "Post123",
    "is_step": 0,
    "is_principle": 0,
    "is_challenge": 1,
    "has_viewed": 0
}]

```

#### Responses 

This should return an array of responses related to a post. **This array is only returned if the post is of type challenge.

```

{
    "rowLabel": "Responses",
    "responses": [{
        "solutionId": "Solution123",
        "thumbnailUrl": "https://thumbnailUrl.com",
        "description": "Test 123",
        "username": "Test",
        "number_of_upvotes": 30,
        "is_accepted": 0,
        "is_declined": 0,
        "has_contributed": 0
    }]
}

```
#### Home-detail should also return arrays for the comments, challenges and users related to the pursuit. 

## Chat.js

#### Messages

The messages array should return an array of messages related to the logged in user.

```

{
    "messages": [{
        "sender": {
            "userPhoto": "https://userPhoto.com",
            "userId": "Test123",
            "username": "Test"
        },
        "message": "Test 123",
        "messageId": "Message123",
        "timestamp": "12424223",
        "postId": "Post124",
        "is_read": 0
    }, {
        "sender": [{
            "userPhoto": "https://userPhoto.com",
            "userId": "Test123",
            "username": "Test"
        }, {
            "userPhoto": "https://userPhoto.com",
            "userId": "Test123",
            "username": "Test"
        }],
        "message": "Test 123",
        "messageId": "Message123",
        "timestamp": "12424223",
        "postId": "Post124",
        "is_read": 0
    }]
}

```

#### Friends

This array should return a list of accounts the user follows.

``` 
"users": [{
    "profiles": [{
        "username": "Test",
        "userId": "Test123",
        "userPhoto": "https://userPhoto.com"
    }]
}]

```

## Triggers

#### The user should receive a trigger when:

1. A user adds them as a friend.
2. A user comments on their pursuit.
3. A user saves their post.
4. A user contribute to their pursuit.  

