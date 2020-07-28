### Altair Library
Altair is a Python API for D3 library in JavaScript. 

All we have to do, is to say:
```python 
Altair.Chart().mark_point().encode(
    x = ##<some_field_in_data>
    y = ##<some_field_in_data>
).interactive()
```
if we add.to_dict() at the end of the code above, it will show the json beinng fed into S3.

It is also possible to get the dictionary above, and save it as a variable (for example spec) and change it a bit, then pass it into Chart.from_dict(spec) object and it will reflect the changes in the new chard. 

We can also add color like this:
```python
.encode(color="Origin:N")
```
by just passing what field we want to pass as different colors but we have to specify the datatype (in this case N as nominal)

Here is how to create a heatmap:
```python
alt.Chart(cars).mark_bar().encode(
    x = alt.X('Miles_per_Gallon', bin=True),
    y = alt.Y('Horsepower', bin=True),
    color = 'count()'
)
````

