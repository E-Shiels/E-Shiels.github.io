---
layout: post
title:      "Eager Loading ActiveRecord Associations"
date:       2018-09-15 19:43:22 +0000
permalink:  eager_loading_activerecord_associations
---


There is a problem within Object Relational Mapping (ORMs) known as SELECT N+1 (or simply as the N+1 problem). It can have a major effect of performance and is related to loading the children of a parent-child relationship.

Let's say we have a program setup with ActiveRecord that shows you the nicknames of 15 major cities and you have to link them to the actual city name. Hopefully we have more than just 15 cities in our database, and if we do, we'll have to find just 15 of them to display. This is where the SELECT N+1 problem comes in. We could code it like this:

```
cities = City.limit(15)

cities.each do |city|
    puts city.nickname
end
```

This would result in **16 total queries**. It would query once to get the 15 cities, and then once per city to find their nicknames. That's more queries than should be necessary to just get 15 cities' nicknames. 

There is a way within ActiveRecord (and other ORMs) to reduce the number of queries from N+1 to 2. It is called Eager Loading. It involves loading the data you want to select from to memory and selecting from it there. This reduces the number of trips to the database and can improve performance for large-scale applications. 

Eager loading is generally done using the method `.includes`. A version of our previous code using `.includes` would look like this:

```
cities = City.includes(:nickname).limit(15)

cities.each do |city|
    puts city.nickname
end
```
Suddenly, the number of queries is reduced to **2**.

`.includes` can be used to load multiple associations by using an array or a hash like this:

```
cities = City.includes(:nickname, :name)
```

`.includes` is technically telling Ruby to choose between two different methods to preload or fetch the data: `.preload` and `.eager_load`. `.preload` runs two queries, one to fetch the primary model and another to fetch associated models. `.eager_load` runs a left outer join and runs one query to fetch both the primary and associate models.

Eager loading isn't particularly important when designing small applications and minimum viable products, but working on scaled up projects, this can greatly improve performance.

	 

	 




References


Active Record Query Interface. (n.d.). Retrieved from Rails Guides: https://guides.rubyonrails.org/active_record_querying.html#eager-loading-associations


Ajith, M. (2014, January 9). The (Silver) Bullet for the N+1 Problem. Retrieved from sitepoint: https://www.sitepoint.com/silver-bullet-n1-problem/


Pettigrew, E. (2016, July 7). 10 Tips for Eager Loading to Avoid n+1 Queries in Rails. Retrieved from Medium: https://medium.com/@codenode/10-tips-for-eager-loading-to-avoid-n-1-queries-in-rails-2bad54456a3f


