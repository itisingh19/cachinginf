# CACHING APPROACHES

## *Why is caching needed?*

What if we try to want some value from large memory but is takes good amount of time or what if we want to load a page but it take a lot of time. Now if we have to access that data and page many times as per requirements? we will be frustrated. Right? we users and developers always wants our requests to process as fast as possible. Cashing provides us the techniques to improve performane and process requests as fast as possible.

## *Lets know what is Caching ?*

Cashing is a technique of storing and accessing data from cache in an efficient way to improve the performance of the application. Data can be any text, image, message or anything. Cashing uses the recently used data and stores the copy of it in cache for future references. So if want some data, we will first look into the cache. If not found then we store the copy of that data into cache after searching in remote system.
we can say that cache is the temporary storage location for copies of the files or data.

### Following are the Caching approaches

## 1. **Populating the cache**

    This approach focuses on storing maximum values in cache so whenever data is requested we can take if directly from cache.
    This have two techniques in it : 

        Upfront population :  
        It says that you should store all the needed values in the cache in the beginning. This can be done when we know what data to store in cache memory. but we do not always know what data is needed or what data should be stored into cache unless a process is made or request is made.

        Lazy Evaluation : 
        In this first we check if data requested is already in cache . If not, then read it from the system and store in cache. Through this techniques copies of data get stored in cache. 

## 2. Keep Cache and Remote System in sync

    When Cache and Remote are in sync,means that data and structure is same and if they are not in sync, it may give us wrong data in return. Techniques :

        Write-through Caching :
        If some new data is written to cache then it is written ti remote system(containing the cache) as well. This caching allows both reading and writing.It can happen only when remote system is the system containing the cache in which new data is stored. Because then it is easy to forward the new writes to the remote system and update cache accordingly.

        Time Based Expiry :
        In this we allow the data in the cache to expire after certain time limit or interval.if the data is expired it is removed from cache. if the data is needed again then it(its updated version if updated) is again inserted into cache. You can easily set the expiration time according to your needs.

        Active Expiry :
        This refers to expire the data from the cache if the same data is modified in remote system. It is necessary to remove wrong data from cacche time to time. This helps in making cache up-to-date as fast as possible. For this to happen it is necessary to detect modified data.

## 3. Managing Cache Size

    We cannot store everthing in cache. System have so much data stored, that all of that can never be stored in cache.We manage cache size by evicting data from cache.Standard eviction techniques are:
        ->  Time Based Eviction : 
            It is similar to time based expiration which also helps in managing cache size.
        ->  First In, First Out(FIFO) :
            It means that when we insert new value in cache, you should remove the earliest value inserted to make space fot new value.
        ->  First In,Last Out(FILO) : 
            It is opposite of FIFO method. This is helpful when the value that were stored first are mostly accessed.
        ->  Least accessed : 
            In this technique, the cache has to keep track of how many times the given data is accessed . The one that is least accessed is removed first.
        ->  Least time between access :
            It counts the number of times the access is made and at what time access was made and then it calculates the average between all accesses. Values that were mostly accessed  earlier but are no more accesses will  have dropping average time between accesses. After sometime average may drop low enough that value will be evicted.

*Reference Link* :
    <https://auth0.com/blog/what-is-caching-and-how-it-works/>
    <http://tutorials.jenkov.com/software-architecture/caching-techniques.html>
