## Project Summary

In this project, you will be guided on how to create a very basic html and css file. There is a guided video that you can follow along with to complete this project.

## Goals

- create an html file
- create a css file
- create a title for your html site
- add a favicon icon to your site
- link your css file to your html file
- have text appear on your website
- be able to change the font and color of the text on your site

## Steps

After each step, use git to add and commit the changes you have made to the project!

### Step 1.

Fork this repository to create your own copy.

### Step 2.

In the terminal on your computer, clone the repositry in your projects folder and cd into the created directory.

<details>

```
cd [path to your project directory];
git clone [github repository url goes here];
cd html-css-intro-guided-project;
```

</details>

### Step 3.

create and html file `index.html`, and css file `index.css`

<details>

```
touch index.html index.css
```

</details>

### Step 4.

create the basic html structure in your html file with html, head and body tags.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>
  <body></body>
</html>
```

</details>

### Step 5.

Using title tags, add a title of `Aloha!` within the head tags in your html.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>
  </head>
  <body></body>
</html>
```

</details>

### Step 6.

Add a an icon image for your site that will show in the browser tab

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
  </head>
  <body></body>
</html>
```

</details>

### Step 7.

Link your css file to your html file using the `link` element

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
    <link href="index.css" rel="stylesheet" />
  </head>
  <body></body>
</html>
```

</details>

### Step 8.

Within the body tags, create a heading using the `h1` element. The heading can say whatever you want! Have fun with this.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
    <link href="index.css" rel="stylesheet" />
  </head>
  <body>
    <h1>My First Website!</h1>
  </body>
</html>
```

</details>

### Step 9.

Add some paragraph texts with the `p` element. You can write whatever you want. Play around with this and create as many paragraphs as you want.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
    <link href="index.css" rel="stylesheet" />
  </head>
  <body>
    <h1>My First Website!</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis. Lorem ipsum dolor sit amet consectetur adipisicing
      elit. Error enim, perferendis non saepe quas fuga. Esse modi dolorem
      voluptatem libero? Ducimus illo esse voluptate labore libero voluptates
      amet nulla vel. Lorem ipsum dolor sit, amet consectetur adipisicing elit.
      Ab dignissimos fugiat quisquam reprehenderit laborum cum veniam, accusamus
      ex aliquid saepe voluptates at error nostrum blanditiis vel minima quos
      porro. Qui.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis.
    </p>
  </body>
</html>
```

</details>

### Step 10.

bring in any font you want from google fonts to add style to your text.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
    <link href="index.css" rel="stylesheet" />
    <link
      href="https://fonts.googleapis.com/css2?family=Red+Rose:wght@300;400;700&display=swap"
      rel="stylesheet"
    />
  </head>
  <body>
    <h1>My First Website!</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis. Lorem ipsum dolor sit amet consectetur adipisicing
      elit. Error enim, perferendis non saepe quas fuga. Esse modi dolorem
      voluptatem libero? Ducimus illo esse voluptate labore libero voluptates
      amet nulla vel. Lorem ipsum dolor sit, amet consectetur adipisicing elit.
      Ab dignissimos fugiat quisquam reprehenderit laborum cum veniam, accusamus
      ex aliquid saepe voluptates at error nostrum blanditiis vel minima quos
      porro. Qui.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis.
    </p>
  </body>
</html>
```

</details>

### Step 11.

In your css file, make the new font from google fonts be the defaut font for all text for your website.

<details>

```css
* {
  font-family: "Red Rose", cursive;
}
```

</details>

### Step 12.

In your css file, select the `h1` heading elements, and make their color `green`

<details>

```css
h1 {
  color: green;
}
```

</details>

### Step 13.

In your css file, select the `p` paragraph elements, and make their color `#485787`;

<details>

```css
p {
  color: #292f33;
}
```

</details>

## Submit project

The final step, and one of the most important! Use git to add and commit any new changes, then push those changes to your reposiroty on github.

Nice work! You have created your first website for this course! You learned a lot in this unit, and your hard work has paid off. Make sure you submit this project in the `Guided project(s)` section for this unit. Just copy the url for your repository, paste it and click send!

## Solution

<details>

<summary>index.html</summary>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
    <link href="index.css" rel="stylesheet" />
    <link
      href="https://fonts.googleapis.com/css2?family=Red+Rose:wght@300;400;700&display=swap"
      rel="stylesheet"
    />
  </head>
  <body>
    <h1>My First Website!</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis. Lorem ipsum dolor sit amet consectetur adipisicing
      elit. Error enim, perferendis non saepe quas fuga. Esse modi dolorem
      voluptatem libero? Ducimus illo esse voluptate labore libero voluptates
      amet nulla vel. Lorem ipsum dolor sit, amet consectetur adipisicing elit.
      Ab dignissimos fugiat quisquam reprehenderit laborum cum veniam, accusamus
      ex aliquid saepe voluptates at error nostrum blanditiis vel minima quos
      porro. Qui.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima
      exercitationem suscipit sed perferendis? Animi iste iure quasi dicta,
      eaque quod velit veritatis, dignissimos neque tenetur fugit minima,
      dolorem tempore quis.
    </p>
  </body>
</html>
```

</details>

<details>

<summary>index.css</summary>

```css
* {
  font-family: "Red Rose", cursive;
}

h1 {
  color: green;
}

p {
  color: #485787;
}
```

</details>
