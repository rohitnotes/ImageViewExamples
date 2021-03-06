# ImageViewExamples（对ImageView封装的类库）

### ShadowImageView库
##### 用法
- 布局中使用
```
<com.cxz.shadowimageview.ShadowImageView
    android:id="@+id/iv_shadowd"
    android:layout_width="300dp"
    android:layout_height="300dp"
    android:layout_marginTop="20dp"
    app:shadowColor="@color/colorPrimary"
    app:shadowRound="5dp"
    app:shadowSrc="@mipmap/lotus" />
```
- 设置图片
```
shadow.setImageResource(resID); 
shadow.setImageDrawable(drawable); 
shadow.setImageBitmap(bitmap);
```
- 设置图片半径
```
shadow.setImageRadius(radius);
```
- 设置图片的阴影颜色
```
shadow.setImageShadowColor(color);
```

##### 效果
![](/screenshot/01.png)


### PaletteImageView库
##### 用法
- 布局中使用
```
<com.cxz.paletteimageview.PaletteImageView
    android:id="@+id/palette"
    android:layout_width="400dp"
    android:layout_height="400dp"
    android:layout_gravity="center_horizontal"
    app:paletteOffsetX="13dp"
    app:paletteOffsetY="13dp"
    app:palettePadding="40dp"
    app:paletteSrc="@mipmap/ez" /> 
```
- 设置半径
```
paletteImageView.setPaletteRadius(progress);
```
- 设置阴影颜色
```
paletteImageView.setShadowColor(color);
```
- 设置阴影的半径
```
paletteImageView.setPaletteShadowRadius(progress);
```
- 设置阴影X的偏移量
```
paletteImageView.setPaletteShadowOffset(progress, 0);
```
- 设置阴影Y的偏移量
```
paletteImageView.setPaletteShadowOffset(0, progress);
```

- 阴影颜色设置图片主色调
```
paletteImageView.setOnParseColorListener(new PaletteImageView.OnParseColorListener() {
	 @Override//解析图片的颜色完毕
	 public void onComplete(PaletteImageView paletteImageView) {
	     int[] vibrant = paletteImageView.getVibrantColor();
	     int[] vibrantDark = paletteImageView.getDarkVibrantColor();
	     int[] vibrantLight = paletteImageView.getLightVibrantColor();
	     int[] muted = paletteImageView.getMutedColor();
	     int[] mutedDark = paletteImageView.getDarkMutedColor();
	     int[] mutedLight = paletteImageView.getLightMutedColor();
	 }
	
	 @Override//解析图片的颜色失败
	 public void onFail() {
	 }
	});  
```

##### 效果
![](/screenshot/02.png)