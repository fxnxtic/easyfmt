# easyfmt
It's tiny and powerful module for customizing your logs with HTML-like tags.

### Features
### Installing
You can use `pip install easyfmt` or `git clone` to install this.

### Syntax
All formatting works by HTML-like tags in `fmt` variable.

### Quick start
```python
import sys
import logging

from easyfmt import EasyFormatter


formatter = EasyFormatter(
    fmt="<italic><bright-black><underline>%(asctime)s</> <italic><black>%(name)s</> [<bold><level>%(levelname)s</>]\t<lvlmsg>%(message)s</>",
    datefmt="%Y-%m-%d %H:%M:%S"
)
logger = logging.getLogger(__name__)
logger.setLevel(logging.DEBUG)
handler = logging.StreamHandler(stream=sys.stdout)
handler.setFormatter(formatter)
logger.addHandler(handler)


logger.critical('System destroyed')
logger.error('Something bad happened.')
logger.warning('123456')
logger.info('Log message with structured logging.')
logger.debug("Database connected")


2025-02-23 12:42:46 __main__ [CRITICAL] System destroyed
2025-02-23 12:42:46 __main__ [ERROR]    Something bad happened.
2025-02-23 12:42:46 __main__ [WARNING]  123456
2025-02-23 12:42:46 __main__ [INFO]     Log message with structured logging.
2025-02-23 12:42:46 __main__ [DEBUG]    Database connected
```

### Contacts
**Telegram:** [@TheDinAlt](https://t.me/TheDinAlt)

`with 💜 by TheDinAlt`
