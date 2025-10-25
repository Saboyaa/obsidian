### Dictionary 
```Python
movie = {"name":"Avengers", "year":2019}
```
- Allows efficient data retrieval based on unique keys
- Flexible and easy 
- Doesn't check the type
### Typed Dictionary
```Python
from typing import TypedDict

class Movie(TypedDict):
	name : str
	year : int

movie = Movie(name="Avengers Endgame", year=2019)
```

- Type Safety
- Enhanced Readability
### Union
```Python
def square(x: Union[int, float]) -> float:
```
- Let's the value be more than one type
### Optional
```Python
def name(x: Optional[str]) -> None:
```
- Make the variable optional to have ( but if it have need to be of a certain type )
### Any
```Python
def square(x: Any) -> float
```
- Let's the value be anything

### Lambda Function
```Python
nums = [1,2,3,4]
squares = list(map(lambda x: x*x,nums))
```
- Just a shortcut to small functions
## Cool Things
### [[LangGraph]]