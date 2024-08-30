# react-native-image-picker kosick 수정본

2024/8/30
google clouds 같은데에서 이미지를 가져올 수 있도록 하기 위해서 수정하였다. / aquarium log 에서 사용하기위함.

ImagePickerModuleImpl.java 파일을 수정하였음.

```java
libraryIntent = new Intent(Intent.ACTION_GET_CONTENT);
libraryIntent.addCategory(Intent.CATEGORY_OPENABLE);
// libraryIntent = new Intent(MediaStore.ACTION_PICK_IMAGES); // kosick - 원래 이거였는데 이럴 경우 google photos 를 못가져오는 문제가 있어서 수정.
```
