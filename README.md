# tarea
Tarea coursera
# functions that cache the inverse of a matrix

# Creates a matrix object that can cache its inverse
makeVector <- function(x = numeric(c)) {

# Initialize a inverse property
        m <- NULL
# Method to set the matrix
        set <- function(y) {
                x <<- y
                m <<- NULL
        }
        
# Method the get the matrix
        get <- function() x
        setmean <- function(mean) m <<- mean
        getmean <- function() m
        list(set = set, get = get,
             setmean = setmean,
             getmean = getmean)
}cachemean <- function(x, ...) {
        m <- x$getmean(c)
        if(!is.null(m)) {
                message("getting cached data")
                return(m)
        }
        data <- x$get(c)
        m <- mean(data, ...)
        x$setmean(m)
        m

