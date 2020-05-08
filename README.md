# **Color Pop**

## Let's play with colors?

### In Color Pop you have three colors to choose, but only one is the correct.

### The color pattern is RGB, i make this project with HTML5, CSS3 and JavaScript.

## A little preview

![image](https://user-images.githubusercontent.com/49375534/81453035-e6999680-915e-11ea-97f1-83d3d3e2af85.png)

## How will this help you?

### Play with Color Pop can help you in your cognitive abilities

> ## Author
| **Where?** | **Wich?** |
|------------|-----------|
|Github|github.com/Arthur-Palhano|
|WebSite|arthur-palhano.github.io|
|Instagram|[@pauloarthr](https://www.instagram.com/pauloarthr/)|
|Email|pauloart.hur670@gmail.com|

## License

[MIT](https://github.com/Arthur-Palhano/Color-Pop/blob/master/LICENSE)

---

## JS Code

```js
var boxes = []

function gerCor() {
    cores = [];

    for (let i = 0; i < 3; i++) {
        cor = [];
        for (let i = 0; i < 3; i++) {
            cor.push(Math.round(Math.random() * 255));
        }
        cores.push(cor);
    }
    return cores;
}


function checkBox() {
    if (boxes.indexOf(this) == boxes[boxes.length - 1]) {
        //Acertou
        score += 1;
    } else if(score != 0){
        //Errou
        score -= 1;
    }
    scoreBox.innerText = `Score: ${score}`
    show();
}

function shine() {
    boxes[boxes.indexOf(this)].style.boxShadow = `3px 3px 20px ${this.style.backgroundColor}`
}

function ashine() {
    boxes[boxes.indexOf(this)].style.boxShadow = `0px 0px 0px`
}

function show() {
    var cores = gerCor();
    var esc = Math.round(Math.random() * 2 + 1) - 1;
    showCol.innerText = `${cores[esc][0]}, ${cores[esc][1]}, ${cores[esc][2]}`

    for (var i = 0; i < 3; i++) {
        window.document.getElementsByClassName("box")[i].style.backgroundColor = `rgb(${cores[i][0]}, ${cores[i][1]}, ${cores[i][2]})`;
        boxes.push(window.document.getElementsByClassName("box")[i])
        boxes[i].addEventListener("click", checkBox)
        boxes[i].addEventListener("mouseover", shine)
        boxes[i].addEventListener("mouseout", ashine)
    }
    boxes.push(esc);
}

var showCol = window.document.getElementById("rgbCol");

var scoreBox = window.document.getElementById("score");
var score = 0;

show()
```
