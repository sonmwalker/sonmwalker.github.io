Whenever I am trying to install any package using pip, I am getting this import error:

```
pip3 install numpy
Traceback (most recent call last):
  File "/usr/bin/pip3", line 9, in <module>
    from pip import main
ImportError: cannot import name 'main'
```

We can clear the error by modifying the pip file.

Check the location of the file:

```
$ which pip
path -> /usr/bin/pip
```

Go to that location(/usr/bin/pip) and open terminal

Enter: `$ sudo nano pip`

You can see:
```
import sys
from pip import main
if __name__ == '__main__':
     sys.exit(main())
```
Change to:

```
mport sys
from pip import __main__
if __name__ == '__main__':
     sys.exit(__main__._main
```
then `ctrl + o` write the changes and exit

Hope this will do!!
