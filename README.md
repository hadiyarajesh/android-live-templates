# Android Live Templates
A collection of Live Templates to use in Android Studio

## Kotlin
1. Create a public/private pair of StateFlow (to hold data in ViewModel)
```kotlin
private val _$VAR$ = kotlinx.coroutines.flow.MutableStateFlow<$TYPE$>()
val $VAR$: kotlinx.coroutines.flow.StateFlow<$TYPE$> get() = _$VAR$
```

<br>

## Jetpack Compose
1. Create a composable function with default modifier
```kotlin
@androidx.compose.runtime.Composable
fun $NAME$(modifier: androidx.compose.ui.Modifier = androidx.compose.ui.Modifier) {
    $END$
}
```

2. Create a composable function that uses a state
```kotlin
@androidx.compose.runtime.Composable
fun $NAME$() {
    var $STATE_NAME$ = androidx.compose.runtime.remember { androidx.compose.runtime.mutableStateOf($INITIAL_VALUE$) }
    $END$
}
```

3. Create a default modifier
```kotlin
modifier: androidx.compose.ui.Modifier = androidx.compose.ui.Modifier
```
