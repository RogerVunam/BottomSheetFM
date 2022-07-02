# BottomSheetFM

# Step1 : Tạo Shape
```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <solid android:color="@android:color/white"/>
    <corners android:topLeftRadius="16dp"
        android:topRightRadius="16dp"/>

</shape>
```


# Step2 : vào theme.xml và đặt tên stype AppBottomSheetDialogTheme1 

```
    <style name="AppBottomSheetDialogTheme1"
        parent="Theme.MaterialComponents.Light.BottomSheetDialog">

        <item name="bottomSheetStyle">@style/CustomBottomSheetStyle</item>
    </style>

    <style name="CustomBottomSheetStyle"
        parent="Widget.Design.BottomSheet.Modal">

        <item name="android:background">@drawable/bottom_sheet_custom</item>
    </style>
```


# Step 3 : Tạo class extend BottomSheetFM override getTheme rồi gọi name stype đặt ở Step2 là xong
```
class ProfileBottomSheetFM : BottomSheetDialogFragment() {
    lateinit var binding: FragmentProfileBottomSheetBinding
    override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {
        binding = FragmentProfileBottomSheetBinding.inflate(layoutInflater)
   
        return binding!!.root
    }

    override fun getTheme(): Int {
        return R.style.AppBottomSheetDialogTheme1
    }
}
```
#Step4: Result
![BottomSheet](https://user-images.githubusercontent.com/108450566/176985106-087e4f1a-6930-4a9d-9961-712fa498f072.png)
