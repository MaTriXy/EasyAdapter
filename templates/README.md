# Code template of ItemController for Android Studio
Copy folder "surf" with template to android_studio_folder/plugins/android/lib/templates and restart Android Studio

Template works in Android Studio 3.0.1 and higher. Java and Kotlin languages are supported.

For using template press Ctrl + Shift + A and type "ItemController".

![using](https://raw.githubusercontent.com/MaksTuev/EasyAdapter/master/templates/template_using.png)

Result:
```kotlin
class ElementItemController(
        private val onClickListener: (element: Element) -> Unit
) : BindableItemController<Element, ElementItemController.Holder>() {

    override fun createViewHolder(parent: ViewGroup): Holder = Holder(parent)

    override fun getItemId(element: Element): Long = element.getId()

    inner class Holder(parent: ViewGroup) : BindableViewHolder<Element>(parent, R.layout.element_layout) {

        private lateinit var element: Element

        init {
            itemView.setOnClickListener { onClickListener.invoke(element) }
            //todo find view here
        }

        override fun bind(element: Element) {
            this.element = element
            //todo render data
        }
    }
}
```
