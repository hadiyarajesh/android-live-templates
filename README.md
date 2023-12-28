# Live Templates
A collection of [Live Templates](https://www.jetbrains.com/help/idea/using-live-templates.html) to use in Android Studio

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

4. Create a Scafold with TopAppBar and a Column
```kotlin
androidx.compose.material3.Scaffold(
    topBar = {
        androidx.compose.material3.TopAppBar(title = { androidx.compose.material3.Text(text = "$TITLE$") })
    }
) { innerPadding ->
    androidx.compose.foundation.layout.Column(
        modifier = androidx.compose.ui.Modifier
            .fillMaxSize()
            .padding(innerPadding)
    ) {
        $END$
    }
}
```

5. Create a Composable Screen with Scaffold, TopAppBar and a Column with sensible default values
```kotlin
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding

@OptIn(androidx.compose.material3.ExperimentalMaterial3Api::class)
@androidx.compose.runtime.Composable
fun $FUNCTION$() {
    androidx.compose.material3.Scaffold(
        topBar = {
            androidx.compose.material3.TopAppBar(title = { androidx.compose.material3.Text(text = "$FUNCTION$") })
        }
    ) { innerPadding ->
        androidx.compose.foundation.layout.Column(
            modifier = androidx.compose.ui.Modifier
                .fillMaxSize()
                .padding(innerPadding),
            verticalArrangement = androidx.compose.foundation.layout.Arrangement.Center,
            horizontalAlignment = androidx.compose.ui.Alignment.CenterHorizontally
        ) {
            $END$
        }
    }
}
```

<br>

# File templates
A collection of [File Templates](https://www.jetbrains.com/help/idea/using-file-and-code-templates.html) to use in Android Studio

1. Create a Hilt based ViewModel
```kotlin
#if (${PACKAGE_NAME} && ${PACKAGE_NAME} != "")package ${PACKAGE_NAME}

#end
#parse("File Header.java")
import javax.inject.Inject
import dagger.hilt.android.lifecycle.HiltViewModel
import androidx.lifecycle.ViewModel

@HiltViewModel
class $NAME @Inject constructor(

) : ViewModel() {
    // Add ViewModel logic here
}
```
