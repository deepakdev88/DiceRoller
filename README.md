# DiceRoller

A simple and clean Android dice roller app built with Jetpack Compose.  
Tap the "Roll" button and watch the dice change—perfect for games, fun, or learning Compose basics!

---

## 📱 Preview

![Screenshot_20250719_160830_DiceRoller](https://github.com/user-attachments/assets/c230e822-7ed6-4c23-aa91-05a21d0fe41c)


---

## ✨ Features

- **Jetpack Compose UI:** Fully modern, declarative design.
- **Random Dice Rolls:** Tap the button to roll and display a random dice face (1–6).
- **Minimalist Design:** Centered dice, soft colors, and a clean look.
- **Responsive Layout:** Works well on all screen sizes.
- **Easy to Customize:** Swap dice images, button styles, or add more features as you wish!

---

## 🛠️ MainActivity Code Example

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            DiceRollerTheme {
                Surface (modifier = Modifier.fillMaxSize()) {
                    DiceRollerApp()
                }
            }
        }
    }
}

@Composable
fun DiceWithButtonAndImage(modifier: Modifier = Modifier){
    var result by remember { mutableStateOf(1) }
    val imageResource = when(result){
        1 -> R.drawable.dice_1
        2 -> R.drawable.dice_2
        3 -> R.drawable.dice_3
        4 -> R.drawable.dice_4
        5 -> R.drawable.dice_5
        else -> R.drawable.dice_6
    }
    Column (
        modifier = modifier,
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        Image(
            painter = painterResource(imageResource),
            contentDescription = result.toString()
        )
        Spacer(modifier = Modifier.height(16.dp))
        Button(onClick = { result = (1..6).random() }) {
            Text(stringResource(R.string.text))
        }
    }
}
```

---

## 🚀 Getting Started

1. **Clone this repo:**
   ```bash
   git clone https://github.com/deepakdev88/DiceRoller.git
   ```
2. **Open in Android Studio**
3. **Build & Run**

---

## 🤝 Contributing

Pull requests, ideas, and improvements are welcome!  
Fork the repo, make your changes, and submit a PR.

---

## 📃 License

Add a license to let others use/contribute to your project!

---

**Made with ❤️ by [deepakdev88](https://github.com/deepakdev88)**
