## Synopsis

This is a simple configurable alert queue for AngularJS.

[Live Demo!](http://bodom0015.game-server.cc/bower_components/angular-alert/demo.html)

## Motivation
While receiving events (from websocket, http, etc), it is sometimes beneficial to display these events to the user. To facilitate with such operations, I have constructed a simple queue service that accepts incoming events and can automatically dismiss them. The user can also choose to manually control the contents of the alert queue if you would prefer to do so.

The user can then bind to this alert queue to display the alert's contents in whatever way they choose.

## Installation
Bower integration coming soon!

Until then, running the following command should retrieve a copy of the source code:
```
git clone https://github.com/bodom0015/angular-alert.git
```

The source code includes a `demo.html` page which illustrates the usage of this module.

To use the module, add a reference to the javascript to your `index.html`:
```
    <script src="/angular-alert/angular-alert.js"></script>
```
    
Add the `ngAlert` module to your module's instantiation and pass the AlertService into your Controller:
```
angular
.module('alertTest', [ 'ngAlert' ])
.controller('AlertController', [ '$scope', 'AlertService', function($scope, AlertService) {
  // Creates a new instance of the alert service
  $scope.service1 = new AlertService();
}]);
```

You should then be able to bind to this service in the view template:
```
<div ng-controller="AlertController">
  <button class="btn btn-success" ng-click="service.enqueue('Message')">Enqueue</button>
  <div class="alert alert-info" ng-repeat="alert in service.alerts">{{ alert.message }}</div>
</div>
```

## License

MIT