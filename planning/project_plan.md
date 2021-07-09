# Project Plan

Pod Members: **Leonel Rivera-Castro, Ashani Jewell, Henry Mu**

## Problem Statement and Description

Problem statement: There's no place to chat about movies and also buy/rent them at the same time. Target audience: Everyone

## User Roles and Personas

- Movie Goers: a user who wants to go to the movies
- Movie Buyer/Renter: a user who wants to buy/rent a movie
- Movie Reviewer: a user who wants to review a movie

Movie goer

    Heather is a 15 year old who is looking to have a fun night out with her friends and wants to see the most popular movie (and age appropriate) that they can talk about later with their classmates the following day. She needs clout and she needs to ensure that her movie selection will provide that.
    Karen is a mother who lives in South Dakota. She is a soccer mom who wants to take her 5 kids to the movies. She is not very good with technology and believes that the vaccines will install microchips. She wants to find PG movies that don’t offend her views or she will call the manager.

Movie buyer

    Timothy is a 30 year old banker who works for Goldman Sachs who doesn’t want to go to the movies alone so he’s looking to buy/rent a movie because he needs some stress relief from his 80 hour shift making $300,000/year.
    Samantha is a 38 year old with 7 children. Since 2 of her children no longer fit the age requirements to get the child price, Samantha is looking at spending upward to $50 at her local theater to entertain both her and her children. As a solution, Samatha is looking to buy/rent a movie that will be fun for the whole family and budget friendly.

Movie reviewer

    Kobe is a 35 year old movie reviewer who is tired of using sites like Reddit and Rotten Tomato to give his opinion on some of the most current movies, as he is unable to find people as passionate as him on those sites. This site allows him to interact with people who are not only as passionate as he is for reviewing movies but allows him to make friends when he never thought that was possible.
    Jessica is a 22 year old college student who recently watched a movie and is fan-girling over the ending of a movie. She wants to find and talk to other people who also share her same excitement.

## User Stories

1. As a movie goer I want to create a profile and interact with people on the forum so that I can talk to other people about Sex in the City.
2. As a movie goer I want to see the highest rated horror movies so I know which ones to watch and I don’t waste my time watching baby ones.
3. As a movie reviewer I want to create a profile and post in the forum so that people can see my opinions about Batman.
4. As a movie buyer I want to be able to browse the different movies in a certain genre and decide which movie to buy based off that.
5. As a movie goer, I want to see the most trending movies in my country to stay connected in the culture around me.
6. As a movie goer, I want to know the closest movie theater to me that will be playing the movies that I look forward to seeing.
7. As a movie goer, I want to find a movie that fits my mood at any time as I will have the choice to pick movies based on genre.
8. As a movie buyer I want to be able to find the most popular movies so it can make my search faster.
9. As a movie reviewer I want to be able to interact with other people’s reviews(commenting, rating, etc).
10. As a movie renter I want to have a clear timeline for when I no longer have access to movies.

## Pages/Screens

List all the pages and screens in the app. Include wireframes for at least 3 of them.
- Home page:
![image](https://user-images.githubusercontent.com/80354834/125115576-83382b00-e0b9-11eb-8710-4724e1077e90.png)

- Cart:
![image](https://user-images.githubusercontent.com/80354834/125115721-b7135080-e0b9-11eb-8d04-08c590212cd5.png)

- Forum:
![image](https://user-images.githubusercontent.com/80354834/125115799-d316f200-e0b9-11eb-9b54-5a7ec21b93a6.png)

- Thread:
![image](https://user-images.githubusercontent.com/80354834/125115832-e0cc7780-e0b9-11eb-93ff-9dddaf716d86.png)

- Make a post:
![image](https://user-images.githubusercontent.com/80354834/125115938-fe014600-e0b9-11eb-81dd-34918881c123.png)

- Search movies:
![image](https://user-images.githubusercontent.com/80354834/125115997-0fe2e900-e0ba-11eb-91fd-1bf28e9a8a1a.png)

- Favorite movies:
![image](https://user-images.githubusercontent.com/80354834/125116048-212bf580-e0ba-11eb-9990-1e0814f98d4b.png)

- Individual movie page:
![image](https://user-images.githubusercontent.com/80354834/125116125-3bfe6a00-e0ba-11eb-8d8f-07c8a43b274e.png)

- Login:
![image](https://user-images.githubusercontent.com/80354834/125116173-4fa9d080-e0ba-11eb-850f-8d8ae40e9dc0.png)

- Register:
![image](https://user-images.githubusercontent.com/80354834/125116221-651efa80-e0ba-11eb-89d8-467734a5cf28.png)

## Data Model

User
| Column name |     Type    | Description |
|:-----------:|:-----------:|:-----------:|
|      id     |   integer   | Primary key |
|   username  | Text UNIQUE |   Username  |
|    email    |     text    |    Email    |
|   password  |     text    |   Password  |
|  firstName  |     text    |  First name |
|   lastName  |     text    |  Last name  |

User Favorites
| Column name |   Type  |        Description       |
|:-----------:|:-------:|:------------------------:|
|   users_id  | integer | References the users(id) |
|   movie_id  | integer |  References the movie_id |

Orders
| Column name |    Type   |        Description       |
|:-----------:|:---------:|:------------------------:|
|      id     |  integer  |        Primary key       |
| customer_id |  integer  | References the users(id) |
|  created_at | timestamp |   Gets the created time  |

Order detail
|            Column name           |   Type  |              Description             |
|:--------------------------------:|:-------:|:------------------------------------:|
| Primary Key (order_id, movie_id) | integer | References the order_id and movie_id |
|             order_id             | integer |         References orders(id)        |
|             movie_id             | integer |         References movie(id)         |
|               price              | integer |              Default 12              |

Forum
| Column name |   Type  | Description |
|:-----------:|:-------:|:-----------:|
|      id     | integer | Primary key |
|     name    |   text  |  Forum name |

Thread
| Column name |    Type    |             Description            |
|:-----------:|:----------:|:----------------------------------:|
|      id     |   integer  |             Primary key            |
|    title    |    text    |      Caption of the subthread      |
|   user_id   |   integer  |         References user(id)        |
|  created_at | timestamp  | Timestamp for when it’s created at |
|   forum_id  |   integer  |      References the forum(id)      |


Post
| Column name |    Type    |             Description            |
|:-----------:|:----------:|:----------------------------------:|
|      id     |   integer  |             Primary key            |
|     text    |    text    |      Caption of the subthread      |
|   user_id   |   integer  |         References user(id)        |
|  created_at | timestamp  | Timestamp for when it’s created at |
|  thread_id  |   integer  |      References the thread(id)     |

## Endpoints

List the API endpoints you will need to implement.
Login 
|  CRUD  | HTTP Verb | Description |   User Stories  |
|:------:|:---------:|:-----------:|:---------------:|
| Create |    POST   |    Login    | Logged in users |
|        |           |             |                 |
|        |           |             |                 |

Post
|  CRUD  | HTTP Verb |  Description  | User Stories |
|:------:|:---------:|:-------------:|:------------:|
| Create |    POST   |   Add a post  |  1, 3, 7, 9  |
|  Read  |    GET    | Read the post |      All     |
| Delete |   DELETE  | Delete a post |  1, 3, 7, 9  |

Register
|  CRUD  | HTTP Verb |  Description  | User Stories |
|:------:|:---------:|:-------------:|:------------:|
| Create |    POST   | Create a user |      All     |
| Delete |   DELETE  | Delete a user |      All     |

Movie Ratings
|  CRUD  | HTTP Verb |   Description   | User Stories |
|:------:|:---------:|:---------------:|:------------:|
| Create |    POST   |  Create ratings |  1, 3, 7, 9  |
|  Read  |    GET    |   Read ratings  |      All     |
| Update |    PUT    | Update a Rating |     7, 9     |
| Delete |   DELETE  |  Delete ratings |  1, 3, 7, 9  |

Order
|  CRUD  | HTTP Verb |     Description    |   User Stories  |
|:------:|:---------:|:------------------:|:---------------:|
| Create |    POST   |   Create an order  | Logged in users |
|  Read  |    GET    | Get list of orders | Logged in users |
| Delete |   DELETE  |   Delete an order  | Logged in users |

Home "/"
|  CRUD  | HTTP Verb |     Description    |   User Stories  |
|:------:|:---------:|:------------------:|:---------------:|
|  Read  |    GET    | Get list of movies | Everyone        |

All Forums (List of Genres)
|  CRUD  | HTTP Verb |     Description    |   User Stories  |
|:------:|:---------:|:------------------:|:---------------:|
|  Read  |    GET    | Get list of Forums | All Users       |

Subforums (List of Threads)
|  CRUD  | HTTP Verb |      Description      |   User Stories  |
|:------:|:---------:|:---------------------:|:---------------:|
| Create |    POST   |   Create an subforum  | Logged in users |
|  Read  |    GET    | Get list of subforums |     Everyone    |
| Delete |   DELETE  |   Delete a subforum   | Logged in users |
| Update |    PUT    |   Update a Subforum   | Logged in Users |

Threads (List of Threads)
|  CRUD  | HTTP Verb |     Description     |   User Stories  |
|:------:|:---------:|:-------------------:|:---------------:|
| Create |    POST   |   Create an thread  | Logged in users |
|  Read  |    GET    | Get list of threads |     Everyone    |
| Delete |   DELETE  |   Delete a thread   | Logged in users |
| Update |    PUT    |   Update a thread   | Logged in Users |


***Don't forget to set up your Issues, Milestones, and Project Board!***

Sprint Plan:
Phase 1/Sprint 1:
Homepage front end
Navbar - Ashani 
Search bar - Leo
Login page - Ashani
Register page - Ashani
Trending Movies - Leo

Homepage Backend
Login Page - Henry 
Register Page - Henry 
JSON Web token - Henry 
Trending movie API call - Henry Leo
Create SQL tables - Henry Leo

Search page Frontend - Leo, Ashani
Search bar
List of movies (cards)
NavBar

Search page Backend - Leo
Create/find the movie API for all movies searched 

Individual movie page front end
Movie poster - Henry
Movie description - Henry
Button for purchasing movie (create an order) - Ashani
Rate a movie -Ashani

Individual move page back end 
Movie API call - Henry
Rate a movie -Ashani

Phase 1/Sprint 2:
Cart Backend 
Orders
Create an order
Delete an order
Checkout (orders list with prices added up)

Cart Frontend
Orders list
Delete an order
Checkout (order list with prices added up)
No tax

Page for all the genres frontend 
List of forums

Page for all the genres backend
API call for list of forums

Phase 2/Sprint 3:

Page for all the subforums frontend
List of threads 

Page for all the subforums backend 
API call for list of threads in that subforum

Page for threads frontend (list of posts)
List of posts
Create a post
Update a post
Delete a post

Page for threads backend (list of posts)
API call to get individual thread with posts
Create a post

Phase 2/ Sprint 4:
HomePage Forum Bar Frontend
Two threads (hardcorded) 
 Button to all threads (page)
Recent posts (of the user)

HomePage Forum Bar Backend
Button to all threads (page)

Individual movie page add threads front end 
Individual movie page add threads back end 

Phase 3/ Sprint 5: (stretch features)
Sidebar (homepage) FrontEnd
Home
Genre
Trending
New Releases
Favorites

Sidebar (homepage) Backend
Home
Genre
Trending
New Releases
Favorites
Google Maps API
Movie Trailer Pop-Up
Sub-sub-forums

