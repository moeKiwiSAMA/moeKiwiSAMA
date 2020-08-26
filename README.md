```kotlin
import org.graalvm.polyglot.*;
import org.graalvm.polyglot.proxy.*;

object Kiwi {
    val name: String by lazy { "moeKiwiSAMA" }
    var programmingLanguage: ArrayList<String> = arrayListOf<String>()

    @JvmStatic
    fun main(args: Array<String>) {
        { "🥝 Kiwi" }.let { me ->
            "🤝 Hi, you can call me ${me()}."
                    .let(::println)
        }

        programmingLanguage
                .also { it.add(Context.create().eval("python", "print('🐍 Python')")) }
                .also { it.add("☕ Kotlin") }
                .also { it.add("🐹 Golang") }
                .also { it.add("🦀 Rust") }
                .let { "I can write some toys in ${it.joinToString()}." }
                .let(::println)
    }

}
```
