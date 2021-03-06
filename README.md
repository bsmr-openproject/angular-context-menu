# [Angular-context-menu](https://github.com/tilt/angular-context-menu)
*An AngularJS directive to set up and open a context menu when a right-click or click event is triggered*

#### Step 1: Install angular-context-menu

Install using Bower:

```
bower install angular-context-menu --save
```

Include angular-context-menu.js or angular-context-menu.min.js in your app.

#### Step 2: Load the ng-context-menu module

```javascript
var app = angular.module('menu-demo', ['ngRoute', 'ng-context-menu'])
```


#### Step 3: Define the context-menu using the context menu factory to glue together a template and a controller

```javascript
angular.module('myApp')

.factory('MyContextMenu', [
  'ngContextMenu',
  function(ngContextMenu) {

  return ngContextMenu({
    controller: 'MyContextMenuController',
    controllerAs: 'contextMenu',
    templateUrl: '/templates/my_context_menu.html'
  });
}])

.controller('MyContextMenuController', [
  '$scope',
  function($scope) {

  $scope.menuEntries = [];
}]);

```

You can explicitly set the ``container`` when setting up the context menu factory.


#### Step 4: Add a context-menu handler to a DOM element

```html
<div has-context-menu
     class="panel panel-default"
     data-target="MyContextMenu"
     locals="some, properties"
  ...
</div>
```

You can list locals, which are properties from the scope of the element opening the menu, which will be forwarded to the context menu scope.

The context menu will get its coordinates by the position of the mouse when the context menu menu receives the (right-) click event.

A demo will be linked in a while.

## Release

Please follow these steps to create a release for the Angular Context Menu:

1. Increase the version number in [bower.json](https://github.com/finnlabs/angular-context-menu/blob/master/bower.json#L3)
2. Run ``gulp``
3. Commit the changes like done in [this commit](https://github.com/finnlabs/angular-context-menu/commit/7fccb0dc52fb34f6be71020f431144f0276e57e3)
4. Create a release in GitHub (see [the documentation](https://help.github.com/articles/creating-releases) for details)
