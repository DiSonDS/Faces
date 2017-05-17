# Faces
# :pensive: →  :grinning:

A Python wrapper around FaceApp.

 ## Basic Usage
 ### With file,
 ```python
import faces

sad = open('sad.jpg', 'rb')
image = faces.FaceAppImage(file=smile)
happy = image.apply_filter('smile', cropped=True)
```
### with URL
 ```python
import faces

old_rockfeller = 'https://upload.wikimedia.org/wikipedia/commons/6/6f/John_D._Rockefeller_1885.jpg'
image = faces.FaceAppImage(url=old_rockfeller)
young_rockfeller = image.apply_filter('young')
```
### or with FaceApp code and device id
```python
import faces

code_of_me_uploaded = '20170517181457gflf'
my_device_id = '12345678'
image = faces.FaceAppImage(code=code_of_me_uploaded, device_id=my_device_id)
brad_pitt = image.apply_filter('hot')
```
## Handling Exceptions
```python
try:
	image = faces.FaceAppImage(...)
except faces.ImageHasNoFaces:
	print('Your face is not recognized. Are you an alian?')
except faces.BaseFacesException:
	print('Some unknown wrong things happened.')
try:
	result = image.apply_filter('young, rich and powerful')
except faces.BadFilterID:
	print('Too cool filter to exist.')
```
## Yes, it's that easy. Now create something cool!