## Firebase Auth

### iOS

Tích hợp Firebase Auth vào Flutter với Android thì có vẻ dễ hơn, hướng dẫn step by step nhanh run được app. Còn với iOS xàm xí hơn. Trên trang chính thức làm theo thì không chạy. Phải đọc file README không phải Firebase Auth, mà của google_sign_in (ios/.symlinks/plugins/google_sign_in/README.md)

Ngoài việc add code giống trên Firebase hướng dẫn, làm thêm thao tác như sau:

Trích dẫn:

1. [First register your application](https://developers.google.com/mobile/add?platform=ios).
2. Make sure the file you download in step 1 is named `GoogleService-Info.plist`.
3. Move or copy `GoogleService-Info.plist` into the `[my_project]/ios/Runner` directory.
4. Open **Xcode**, then right-click on `Runner` directory and select `Add Files to "Runner"`.
5. Select `GoogleService-Info.plist` from the file manager.
6. A dialog will show up and ask you to select the targets, select the `Runner` target.
7. Then add the `CFBundleURLTypes` attributes below into the `[my_project]/ios/Runner/Info.plist` file.

```xml
<!-- Put me in the [my_project]/ios/Runner/Info.plist file -->
<!-- Google Sign-in Section -->
<key>CFBundleURLTypes</key>
<array>
	<dict>
		<key>CFBundleTypeRole</key>
		<string>Editor</string>
		<key>CFBundleURLSchemes</key>
		<array>
			<!-- TODO Replace this value: -->
			<!-- Copied from GoogleService-Info.plist key REVERSED_CLIENT_ID -->
			<string>com.googleusercontent.apps.861823949799-vc35cprkp249096uujjn0vvnmcvjppkn</string>
		</array>
	</dict>
</array>
<!-- End of the Google Sign-in Section -->
```
