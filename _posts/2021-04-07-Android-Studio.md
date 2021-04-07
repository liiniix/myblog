Two fundamental concepts:

- **App provide different entry point:** Androoid app is a combination of components. Components can be invoked individually.
> *activity* is a type of app component with UI.
> *main activity* is invoked when user types app icon.
> User can be directed from notification or another app too.
> *broadcast receiver* and *services* are components which perform background tasks without UI.

- **App adapts to different devices:** Android provides different resources to different devices eg: different layout for different sreen sizes which is determined autometically.

**app > java > com.example.myfirstapp > MainActivity**: It is entry point.
**app > res > layout > activity_main.xml**: UI for `MainActivity`.
**app > manifests > AndroidManifest.xml**: Fundamental characteristics are defined here.
**Gradle Scripts > build.gradle**: Gradle plugin generation.

UI of android app are built on hierarchy of `layouts` and `widgets`.
Layouts are `ViewGroup` containing how their child views are positioned.
Widgets are `View` such as buttons and text objects.
![]({{site.url}}/{{site.baseurl}}/assets/android/hierarchy.png)