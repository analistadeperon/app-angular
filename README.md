# app-angular
 <title>AngularJS & Firebase Web App</title>
 
    <link href="http://getbootstrap.com/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="http://getbootstrap.com/examples/signin/signin.css" rel="stylesheet">
 
    <link href="justified-nav.css" rel="stylesheet">
 
</head>
 
<body>
 
    <div class="container">
        <div class="jumbotron" style="padding-bottom:0px;">
            <h2>AngularJS & Firebase App!</h2>
        </div>
        <form class="form-signin" role="form">
            <input type="email" class="form-control" placeholder="Email address" required="" autofocus="">
            <input type="password" class="form-control" placeholder="Password" required="">
            <label class="checkbox">
                <a href="#"> Sign Up</>
        </label>
        <button class="btn btn-lg btn-primary btn-block" type="submit">Sign in</button>
      </form>
 
    </div>
 'use strict';
 
angular.module('myApp.home', ['ngRoute'])
 
// Declared route 
.config(['$routeProvider', function($routeProvider) {
    $routeProvider.when('/home', {
        templateUrl: 'home/home.html',
        controller: 'HomeCtrl'
    });
}])
 
// Home controller
.controller('HomeCtrl', [function() {
 
}]);
'use strict';
 
angular.module('myApp', [
    'ngRoute',
    'myApp.home'           // Newly added home module
]).
config(['$routeProvider', function($routeProvider) {
    // Set defualt view of our app to home
     
    $routeProvider.otherwise({
        redirectTo: '/home'
    });
}]);
<script src="home/home.js"></script>
<script src="https://cdn.firebase.com/js/client/1.0.18/firebase.js"></script>
<script src="https://cdn.firebase.com/libs/angularfire/0.8.0/angularfire.min.js"></script>
<script src="https://cdn.firebase.com/js/simple-login/1.6.2/firebase-simple-login.js"></script>
angular.module('myApp.home', ['ngRoute','firebase'])
$scope.SignIn = function($scope) {
    var username = $scope.user.email;
    var password = $scope.user.password;
     
    // Auth Logic will be here
}
var firebaseObj = new Firebase("https://blistering-heat-2473.firebaseio.com");
.controller('HomeCtrl', ['$scope','$firebaseSimpleLogin',function($scope,$firebaseSimpleLogin) {
  .controller('HomeCtrl', ['$scope','$firebaseSimpleLogin',function($scope,$firebaseSimpleLogin) {
    $scope.SignIn = function(event) {
    event.preventDefault();  // To prevent form refresh
    var username = $scope.user.email;
    var password = $scope.user.password;
     
    loginObj.$login('password', {
            email: username,
            password: password
        })
        .then(function(user) {
            // Success callback
            console.log('Authentication successful');
        }, function(error) {
            // Failure callback
            console.log('Authentication failure');
        });
}
<body ng-controller="HomeCtrl">
 
    <div class="container">
        <div class="jumbotron" style="padding-bottom:0px;">
            <h2>AngularJS & Firebase App!</h2>
        </div>
        <form class="form-signin" role="form">
            <input ng-model="user.email" type="email" class="form-control" placeholder="Email address" required="" autofocus="">
            <input ng-model="user.password" type="password" class="form-control" placeholder="Password" required="">
            <label class="checkbox">
                <a href="#"> Sign Up</>
        </label>
        <button type="button" class="btn btn-lg btn-primary btn-block">SignIn</button>
      </form>
 
    </div>
 
   
 
	
<button type="button" ng-click="SignIn($event)" class="btn btn-lg btn-primary btn-block">SignIn</button>

   
 
