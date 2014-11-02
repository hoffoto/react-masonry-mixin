React Masonry Mixin
===================

#### TODO
* Test suite

#### Introduction:
A mixin for React.js to create masonry

#### Usage:

* You will have to use Masonry as a script dependency, as there is no complete npm module available at the moment.
`<script src='//cdnjs.cloudflare.com/ajax/libs/masonry/3.1.5/masonry.pkgd.min.js' />`

* To use the mixin
 * require the mixin
 * use the mixin in your component
 * add `ref="masonryContainer"` to the container you want to apply the effect on

* example use in code

```js
/** @jsx React.DOM */
 
'use strict';
 
var React = require('react');
 
var MasonryMixin = require('react-masonry-mixin');
 
var masonryOptions = {
    transitionDuration: 0
};
 
module.exports = React.createClass({
    displayName: 'SomeComponent',
 
    mixins: [MasonryMixin(masonryOptions)],
 
    render: function () {
        var childElements = this.props.elements.map(function(element){
           return (
                <div className="someclass">
                    {element.name}
                </div>
            );
        });
        
        return (
            <div ref="masonryContainer">
                {childElements}
            </div>
        );
    }
});
```