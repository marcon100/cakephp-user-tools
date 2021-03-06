Quick Start
==========

If you database follows the schema the plugin expects to work with you can simply kick start your users in the application by just adding the component and helper.

In \App\Controller\UsersController:

```php
UsersController extends AppController {
	public function initialize() {
		parent::initialize();
		$this->loadComponent('Burzum/UserTools.UserTool');
	);
}
```

In your \App\View\AppView:

```php
class AppView extends View {
	public function initialize() {
		parent::initialize();
		$this->loadHelper('Burzum/UserTools.Auth');
	}
}
```

The component will take the main model of the controller and load the ```UserBehavior``` with it's default settings.

Go to ```/users/register``` and try to register, make sure your email config is set up properly.

You should receive an email notification with a token and a verification URL. After verifying your user go to ```/users/login``` and try to login.