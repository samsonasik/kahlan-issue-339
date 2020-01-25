Step to reproduce
-----------------

```bash
git clone git@github.com:samsonasik/kahlan-issue-339.git

composer install

vendor/bin/kahlan --coverage=1
```

The error is happen because using `https://github.com/laminas/laminas-zendframework-bridge`

It will output error:

```bash
$ vendor/bin/kahlan --coverage=1                                      

PHP Fatal error:  Uncaught Error: Cannot use object of type Closure as array in /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Jit/ClassLoader.php:114
Stack trace:
#0 /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Reporter/Coverage/Collector.php(121): Kahlan\Jit\ClassLoader::instance()
#1 /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Reporter/Coverage.php(83): Kahlan\Reporter\Coverage\Collector->__construct(Array)
#2 /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Cli/Kahlan.php(557): Kahlan\Reporter\Coverage->__construct(Array)
#3 [internal function]: Kahlan\Cli\Kahlan->Kahlan\Cli\{closure}(Object(Closure))
#4 /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Filter/Filters.php(204): call_user_func_array(Object(Closure), Array)
#5 [internal function]: Kahlan\Filter\Filters::Kahlan\Filter\{closure}()
#6 /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Filter/Filters.php(206): call_user_func_array(Object(Closure), Array)
#7 /Users/s in /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Jit/ClassLoader.php on line 114

Fatal error: Uncaught Error: Cannot use object of type Closure as array in /Users/samsonasik/www/kahlan-issue-339/vendor/kahlan/kahlan/src/Jit/ClassLoader.php on line 114
```
