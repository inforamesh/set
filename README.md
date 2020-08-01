# Set

## About Set

It is a custom set class in JavaScript similar to Set in es2015. It has total 7 methods, Description of every method is underfollowed.

## Methods

* add() - Adds an element to the set.
* has() - Checks whether a particular element exists or not in set.
* values() - Returns all the values on the set.
* remove() - Removes an element from the set.
* union() - Returns union of two sets.
* intersection() - Returns intersection of two sets.
* difference() - Returns the difference of two sets.

## Code

```
/**
 * This is an implementation of custom set class.
 * @author Ramesh Kumar
 *
 */

class Set {
    
    /**
     * initialization of an object.
     */
    constructor() {
        this.collection = [];
    }

    /**
     * Adds an element to the set.
     * @param Set value an element for Set
     */
    add(value) {
        if (!this.has(value)) {
            this.collection.push(value);
            return true;
        }

        return false;
    }

    /**
     * Checks weather a particular element is exists or not in set.
     * @param Set value an element of Set.
     */
    has(value) {
        if (this.collection.indexOf(value) !== -1) {
            return true;
        }

        return false;
    }

    /**
     * Returns all the values on the set.
     */
    values() {
        return this.collection;
    }

    /**
     * Removes an element from the set.
     * @param Set value an element of Set.
     */
    remove(value) {
        if (this.has(value)) {
            var index = this.collection.indexOf(value);
            this.collection.splice(index, 1);
            return true;
        }

        return false;
    }

    /**
     * Returns union of two sets.
     * @param Set otherSet object of set. 
     */
    union(otherSet) {
        var set = new Set();

        this.collection.forEach(element => {
            set.add(element);
        });

        otherSet.values().forEach(element => {
            set.add(element);
        });

        return set;
    }

    /**
     * Returns intersection of two sets.
     * @param Set otherSet object of set.
     */
    intersection(otherSet) {
        var set = new Set();

        this.collection.forEach(element => {
            if (otherSet.has(element)) {
                set.add(element);
            }
        });

        return set;
    }

    /**
     * Returns difference of two sets.
     * @param Set otherSet object of set.
     */
    difference(otherSet) {
        var set = new Set();

        this.collection.forEach(element => {
            if (!otherSet.has(element)) {
                set.add(element);
            }
        });

        return set;
    }
}

var set = new Set();
set.add(10);
set.add(20);
set.add(30);

var set1 = new Set();
set1.add(20);
set1.add(40);


console.log(set.values());
console.log(set.has(10));
set.remove(10);
console.log(set.has(10));
set.add(40);
console.log(set.values());
console.log(set.union(set1));
console.log(set.intersection(set1));
console.log(set.difference(set1));
```
