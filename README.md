# Laravel and Vue.js ToDo List

A test project built to explain the power of the Laravel + Vue.js union.
I'm glad to say this is my very firt real experience with Vue.js, so let's see what happens.

## Serving

The main idea here is to see how Vue.js routes can be integrated do the Laravel routes, if there's a lot of hard work to spend on this and to know the benefits os adopting those technologies in the same project, intead of creating two separate apps in both environments.
I'm starting with an Apache 2.4 server, adoptin PHP 7.4 as my default version and, before starting to code, tendind to use Vue.js to test the Inertia.js default setup witch comes with the Laravel 8, the choosen version of the framework.

## Installation

If you wanna run this project in a local environment, just be sure you have PHP >= 7.4, with the default Laravel extensions enabled, composer, Node > 12 and MySQL install. Once you're ready, just enter the following commands ar your bash:

```
composer install
npm install
php artisan migrate
```

## Development diary

### Day 1

Inertia.js was left aside by now. My very first goal is to know the Vue.js core, so I dicided to use only Vue.js 2 in it's root mode!

The first part was going to my known area and to build the API routes, the CRUD and test them with Insomnia. The test call's ar attached in the project, at the /data folder. Here I could not find any trouble. I consider myself a good Laravel specialized dev, so if I'd lost any high time at this point, I should sereusly think about changing my working area. Of course I'm kidding about it, but was really easy to pass the first level. As the objective here is to improve the frontend skills (Vue.js for been more specific), I've left the stuff very simple at the backend side. No auth, no high security techniques. It's just an open API CRUD.

Once backend was ready, I decided to look for a tutorial, to learn the whole thing right. So I strated to create de Vue.js file structure inside the resources folder. Now the app.vue file and the App compontent was at the right place. So I decided to change the welcome blade file for loading the Vue.js app by my own.

My first version, finished in 2 hours with a lot of researching and trying to be the most independent as posssible, contains an application very poor at the front. Every single API return I get in axios sends an event to the mais Vue.js file, witch reloads the full list of items from the API. I known this is weird and not recomended, but we're talking about a first try with a new concept. The impressions and the excitement are the best. If were't so late night, I would still be coding.

### Day 2 (comes next...)

Although I'm very excited with the Vue.js (or any JS framework actually) way of doing the front end stuff, I also know that a very small project like this will only give me a bit of the vision of the whole world. So, I decided to give one more day to the project to set the bar a little higher. I want to learn the concept and how to work with States, avoiding the massive number of list reloadings I left in the code. Once it's done, I gonna go to a more complex idea, as like a chat or anything like that.