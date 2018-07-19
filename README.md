Gradle Define Custom Task Demo
==============================

How to define custom task in `build.gradle`.

I was thinking to define a simplest gradle task is like this:

```
task hello() {
    println("Hello, gradle")
}
```

But it's totally wrong.

The `{ println("Hello, gradle") }` part is executed when configurating the `build.gradle` script, for only one time.

With this code, you will confuse why it always prints `Hello, gradle` even if you are running a different task, and sometimes, it doesn't output anything when you run `gradle hello`?

The correct version is:

```
task hello() {
    doLast {
        println("Hello, gradle")
    }
}
```

see more in `build.gradle`

Run:
----

```
./gradlew hello
```

or

```
./gradlew hello2
```