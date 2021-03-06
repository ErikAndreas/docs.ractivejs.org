[[Home]] > [[API reference]] > [[ractive.merge()]]

Merges data from one array into another, inserting and removing nodes from the DOM as necessary. This is an efficient way to (for example) handle data from a server.

Where necessary, items are moved from their current location in the array (and, therefore, in the DOM) to their new location. To determine whether the first item of `['foo', 'bar', 'baz']` is the same as the last item of `['bar', 'baz', 'foo']`, by default we do a strict equality (`===`) check.

In some situations that won't work, because the arrays contain objects, which may *look* the same but not be identical. To deal with these, we use the `compare` option detailed below.

> ### ractive.merge( keypath, value[, options] )
> > #### **keypath** *`String`*
> > The [keypath](keypaths) of the array we're updating
> > #### **value** *`Array`*
> > The new data to merge in
> > #### options *`Object`*
> > > #### compare *`Boolean` or `String` or `Function`*
> > > If `true`, values will be stringified (with `JSON.stringify`) before comparison. If you pass a string such as `"id"`, array members will be compared on the basis of their properties of that name. Alternatively, pass a function that returns a value with which to compare array members.
> > > #### complete *`Function`*
> > > A function that will be called after any [[transitions]] triggered by the merge are complete.