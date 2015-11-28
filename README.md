# KotSharedPreferences

## Usage

Before:

```java
SharePreferences prefs = PreferenceManager.getDefaultSharedPreferences(context);
SharePreferences.Editor editor = prefs.edit();
editor.putString("name", "Andrew Chen");
editor.putInt("age", 18, 14);
editor.apply();
```

After:

```kotlin

User(context).edit() {
  name = "Andrew Chen"
  age = "18"
}

public class User(context: Context) : Preferences(context) {
  var name: String by Preference()
  var age: Int by Preference(default = 14)
}
```

or

```kotlin
User user = User(context)
user.name = "Andrew Chen"
user.age = 18

public class User(context: Context) : Preferences(context) {
  var name: String by Preference()
  var age: Int by Preference(default = 14)
}
```
