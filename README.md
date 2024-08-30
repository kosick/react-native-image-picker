# react-native-image-picker kosick 수정본

https://stackoverflow.com/questions/77291763/how-to-enable-browse-option-in-photo-picker-android (2024/6/20 kosick 참고)

2024/8/30
google clouds 같은데에서 이미지를 가져올 수 있도록 하기 위해서 수정하였다. / aquarium log 에서 사용하기위함.

ImagePickerModuleImpl.java 파일을 수정하였음.

```java
libraryIntent = new Intent(Intent.ACTION_GET_CONTENT);
libraryIntent.addCategory(Intent.CATEGORY_OPENABLE);
// libraryIntent = new Intent(MediaStore.ACTION_PICK_IMAGES); // kosick - 원래 이거였는데 이럴 경우 google photos 를 못가져오는 문제가 있어서 수정.
```


2024/6/21
react-native-image-picker
-> 구글 클라우드(photo) 에서 사진 가져올 때 문제있다고해서 'Browse' 옵션을 활성화 시키려면 아래와 같이 libraryIntent 코드를 고쳐야했다.
따라서 patch-package 들어갔음.
// libraryIntent = new Intent(MediaStore.ACTION_PICK_IMAGES); -> kosick: 이걸 사용할 경우 google photos 를 못 사용함.
libraryIntent = new Intent(Intent.ACTION_GET_CONTENT);
libraryIntent.addCategory(Intent.CATEGORY_OPENABLE);
