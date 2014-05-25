Provider that allows you to configure routes using the configuration file.

```ini
[routes]

0.route = "/admin/users/my-profile"
0.controller = "user"
0.action = "profile"

1.route = "/admin/:controller/a/:action/:params"
1.controller = 1
1.action = 2
1.params = 3

2.route = "/news/([0-9]{4})/([0-9]{2})/([0-9]{2})/:params"
2.controller = "posts"
2.action = "show"
2.year = 1
2.month = 2
2.day = 3
2.params = 4

3.route = "/documentation/{chapter}/{name}.{type:[a-z]+}"
3.controller = "documentation"
3.action = "show"

4.route = "/posts/{year:[0-9]+}/{title:[a-z\-]+};Posts::show"

41.route = "/posts/{year:[0-9]+}/{title:[a-z\-]+}"
41._param = Posts::show

5.route = "/news/{country:[a-z]{2}}/([a-z+])/([a-z\-+])"
5.section = 2
5.article = 3

6.route = "'/:module/:controller/:action/:params"
6.module = 1
6.controller = 2
6.action = 3
6.params = 4

7.route = "/login"
7.module = "backend"
7.controller = "login"
7.action = "index"

8.route = "/products/:action"
8.module = "frontend"
8.controller = "products"
8.action = 1

9.route = "/:namespace/login"
9.namespace = 1
9.controller = "login"
9.action = "index"

10.route = "/login"
10.namespace = "Backend\Controllers"
10.controller = "login"
10.action = "index"

11.route = "/products/edit/{id};Products::edit"
11._get = true

12.route = "/products/save;Products::save"
12._post = true

13.route = "/products/update"
13._post = true
13._put = true

14.convert!!!!

15.group.0.module = "blog"
15.group.0.controller = "index"
15.group.0.preffix = "/blog"
15.group.0._host = "blog.mycompany.com"
15.group.0.routes.0.route = "/save"
15.group.0.routes.0.action = "save"
15.group.0.routes.1.route = "/edit/{id}"
15.group.0.routes.1.action = "edit"
15.group.0.routes.2.route = "/blog"
15.group.0.routes.2.controller = "blog"
15.group.0.routes.2.action = "index"

16.route = "/posts/{year}/{title};Posts::show"
16._name = "show-posts"

_default = false

_404.controller = "index"
_404.action = "route404"

_default.module = "backend"
_default.namespace = "Backend\Controllers"
_default.controller = "index"
_default.action = "index"

_removeExtraSlashes = ture


17.beforeMatch!!!

18.route = "/login"
18.module = "admin"
18.controller = "session"
18.action = "login"
18._host = "admin.company.com"

19.route = "/login"
19.module = "admin"
19.controller = "session"
19.action = "login"
19._host = "([a-z+]).company.com"

_uriSource = 'get'
_uriSource = 'server'
```