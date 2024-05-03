## AngularJS codes
### hello world using angularjs
``` 
<div ng-app="myApp" ng-controler="myController">
  <h1>{{ message }}</h1>
</div>

<script>
  const app = angular.module('myApp', [])
  app.controller('myController', function($scope) {
    $scope.message = "Hello, World!"
})
</script>
```

### code using ng-model
```
<div ng-app="myApp" ng-controller="myController">
  <label for="nameInput">Enter name: </label>
  <input type="text" ng-model="userName">
  <p>Hello, {{ userName }}!</p>
</div>
```

### code using ng-click
```
<button ng-click="count = count + 1" ng-controller="myCtrler">Increment</button>
<p>Count: {{ couunt }}</p>
<script>
  const app = angular.module('myApp', [])
  app.controller('myCtrl', function($scope) {
    $scope.count = 0
})
</script>
```

### services in angularjs
```
<div ng-app="myApp" ng-controller="myCtrl">
  <p>The url of this page is:</p>
  <h3>{{myUrl}}</h3>
</div>

<script>
  const app = angular.module('myApp', [])
  app.controller('myCtrl', function($scope, $location) {
    $scope.myUrl = $location.absUrl()
</script>
```

### Form validation
```
<div ng-controller="FormController">
    <form name="myForm" ng-submit="submitForm()" novalidate>
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" ng-model="user.name" required>
        <span ng-show="myForm.name.$error.required">Name is required</span>
        
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" ng-model="user.email" required>
        <span ng-show="myForm.email.$error.required">Email is required</span>
        <span ng-show="myForm.email.$error.email">Invalid email address</span>

        <button type="submit" ng-disabled="myForm.$invalid">Submit</button>
    </form>

    <div ng-if="submitted">
        <p>Submitted!</p>
        <p>Name: {{ user.name }}</p>
        <p>Email: {{ user.email }}</p>
    </div>
</div>

<script>
    angular.module('myApp', [])
        .controller('FormController', function($scope) {
            $scope.user = {};
            $scope.submitted = false;

            $scope.submitForm = function() {
                if ($scope.myForm.$valid) {
                    // Form is valid, do something with the data
                    $scope.submitted = true;
                }
            };
        });
</script>
```

### custom directive
```
<div ng-controller="MainController">
    <h1>Custom Directive Example</h1>
    <custom-greeting name="John"></custom-greeting>
</div>

<script>
    angular.module('myApp', [])
        .directive('customGreeting', function() {
            return {
                restrict: 'E', // Restrict usage to element
                scope: {
                    name: '@' // Bind the name attribute to the scope
                },
                template: '<p>Hello, {{ name }}!</p>'
            };
        })
        .controller('MainController', function($scope) {
            // Main controller logic here
        });
</script>
```
