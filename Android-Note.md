
### FullScreen DialogFragment
```java

    @Override
    public void onCreate(@Nullable final Bundle savedInstanceState) {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
            setStyle(STYLE_NO_TITLE, android.R.style.Theme_Material_Light_NoActionBar_Fullscreen);
        } else {
            setStyle(STYLE_NO_TITLE, android.R.style.Theme_DeviceDefault_Light_NoActionBar);
        }

        super.onCreate(savedInstanceState);

    }
    
    @Override
    public void onStart() {
        super.onStart();
        Dialog dialog = getDialog();
        if (dialog != null) {
            int width = ViewGroup.LayoutParams.MATCH_PARENT;
            int height = ViewGroup.LayoutParams.MATCH_PARENT;
            dialog.getWindow().setLayout(width, height);
            dialog.getWindow().setBackgroundDrawable(new ColorDrawable(Color.BLACK));
            getDialog().getWindow().addFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN);
            getDialog().getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS);
        }

    }

```
##OR
```java
    <style name="FullScreenDialog" parent="android:Theme" >
        <item name="android:backgroundDimEnabled">false</item>
        <item name="android:windowNoTitle">true</item>
        <item name="android:padding">0dp</item>
        <item name="android:windowIsFloating">false</item>
        <item name="android:windowBackground">@android:color/white</item>
    </style>
        @Override
    public int getTheme() {
        return R.style.FullScreenDialog;
    }
```
