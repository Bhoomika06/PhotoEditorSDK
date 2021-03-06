# PhotoEditorSDK

![alt tag](https://s18.postimg.org/xza5yw53d/photoeditorsdk.png)

Photo Editor SDK contains a lot of features like edit, scale, rotate and draw on images like Instagram stories.

-----------------------------------------------------------------------------------------------------

# Application Features
1. Adding **Images**.
2. Adding **Stickers**.
3. Adding **Text** with option to change its **Color**.
4. **Drawing** on image with option to change its **Color**, its **Size** and **Erasing**.
5. **Scaling** and **Rotating** views.
6. **Deleting** views.
7. **Saving** photo after editing.
8. **Undo** after adding views.

-----------------------------------------------------------------------------------------------------

# User Documentation :

1. First of all you have to get instance of PhotoEditorSDK to initialize it and start calling the desired functions.
```java
photoEditorSDK = new PhotoEditorSDK.PhotoEditorSDKBuilder(PhotoEditorActivity.this)
//add the parent image view
.parentView(parentImageRelativeLayout)
//add the desired image view
.childView(photoEditImageView)
//add the deleted view that will appear during the movement of the views
.deleteView(deleteRelativeLayout)
// add the brush drawing view that is responsible for drawing on the image view
.brushDrawingView(brushDrawingView)
// build photo editor sdk
.buildPhotoEditorSDK();
```

2. To add **Text** on the image:
```java
photoEditorSDK.addText(String text, int colorCodeTextView);
```

3. To add **Image** or **Stickers**:
```java
photoEditorSDK.addImage(Bitmap desiredImage);
```

4. To add **Emoji**:
```java
photoEditorSDK.addEmoji(String emojiName, Typeface emojiFont);
```

5. To **Draw** on the image:
```java
photoEditorSDK.setBrushDrawingMode(boolean brushDrawingMode);
// brushDrawingMode is false by default, true if you want to draw on the image view
```

6. To change the **Color** and **Size** of the drawing view.
```java
photoEditorSDK.setBrushSize(int size);
photoEditorSDK.setBrushColor(int colorCode);
```

7. To apply **The Eraser** option, change its **Size** and the **Color** of it:
```java
photoEditorSDK.brushEraser();
photoEditorSDK.setBrushEraserSize(float brushEraserSize);
photoEditorSDK.setBrushEraserColor(int color);
```

8. To **Save** the image after editing:
```java
photoEditorSDK.saveImage(folderName, imageName);
```

9. To **Undo** the added **Views (Image or Text)**:
```java
photoEditorSDK.viewUndo();
```

10. To **Clear All** the added **Views (Image or Text)**:
```java
photoEditorSDK.clearAllViews();
```

11. To **Clear All** the added **Drawing Views**:
```java
photoEditorSDK.clearBrushAllViews();
```

12. To listen on **Added Views**, **Edit the added Text Views**, **Added and Removed Views** and **Start and Stop Moving Views**. You can implement:
```java
photoEditorSDK.setOnPhotoEditorSDKListener(new OnPhotoEditorSDKListener() {
    @Override
    public void onEditTextChangeListener(String text, int colorCode) {
    
    }
    @Override
    public void onAddViewListener(ViewType viewType, int numberOfAddedViews) {
    
    }
    @Override
    public void onRemoveViewListener(int numberOfAddedViews) {
    
    }
    @Override
    public void onStartViewChangeListener(ViewType viewType) {
    
    }
    @Override
    public void onStopViewChangeListener(ViewType viewType) {
    
    }
});
```
-----------------------------------------------------------------------------------------------------

# Future Work

**Will add this library in maven and jcenter very soon. To integrate PhotoEditorSDK to your project all what you need is to clone the project and import PhotoEditorSDK module to your project.**

-----------------------------------------------------------------------------------------------------

# To Contribute

1. Fork this repository.
2. Make your edits.
3. TEST THEM!
4. Create a pull request

-----------------------------------------------------------------------------------------------------

# License

Copyright (c) 2017 Ahmed Adel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

