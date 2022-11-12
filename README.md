This blog will show you how you can create a game in golang using [ebitenEngine](https://github.com/hajimehoshi/ebiten) and publish it on your github account.
For example of this blog, we'll create a simple snake game and show examples below. If you just want to skip the whole building this game process and straight ahead dive into the source code, you can do so here [snake example](https://github.com/hajimehoshi/ebiten/blob/main/examples/snake/main.go).
This blog is meant for someone who is new/intermediate to game development and want to use golang to create a game. Or if you are learning Golang, then creating a game is a great way to build skills in it.

### Creating a project
First of all start with initializing your github project.
```
mkdir snake && cd snake
git init
```
Create a file main.go.
Now we'll configure go modules
```
go mod init github.com/<yourName>/Snake
```
This will generate go.mod and go.sum.

### Setting up Screen
We are setting up the screen width and height as 640x480. You can change it as per your liking. 
```
const (
	screenWidth        = 640
	screenHeight       = 480
)
```

// Some paragraph here for understanding below apis
```
func (g *Game) Update() error {
	return nil
}

func (g *Game) Draw(screen *ebiten.Image) {
}

func (g *Game) Layout(outsideWidth, outsideHeight int) (int, int) {
	return screenWidth, screenHeight
}

type Game struct {
}

func main() {
	ebiten.SetWindowSize(screenWidth, screenHeight)
	ebiten.SetWindowTitle("Snake (Ebitengine Demo)")
	if err := ebiten.RunGame(&Game{}); err != nil {
		log.Fatal(err)
	}
}
```

![This is an image](https://github.com/Ishmeet/Blogs-Snake/blob/main/image1.png)

