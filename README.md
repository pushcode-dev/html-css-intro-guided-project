### Important note

When going through this project, I noticed some issues with the `prettier` code formatter in VSCode when formatting html. Especially with formatting `<cite>`, `<a>`, and `<blockquote>` elements. In fact, the `<blockquote>` element completely prevented the formatter from formatting. Because of this, I switched over to using VSCode's html formatter. To do this, I opened the `command palette` (CMD + Shift + P on mac), and searched for `Open Settings (JSON)` and clicked on the option.

This is what my my settings.json file contains now:

```json
{
  "window.zoomLevel": 1,
  "editor.formatOnSave": true,
  "files.autoSave": "onFocusChange",
  "editor.tabSize": 2,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.wordWrap": "on",
  "[html]": {
    "editor.defaultFormatter": "vscode.html-language-features"
  }
}
```

## Project Summary

In this project, we will add to the `Gallo Pinto Recipe` website we started in the last unit. We will group elements together and add pictures, backgrounds, form elements and use the box-model to make the website more interesting and fun.

## Goals

- add images using the html <img> element
- add images using the css background-image property
- understand the box model and how to manipulate margin, border, and padding
- group elements together using the <div> element
- use sematic html
- understand width and height
- use and style html form elements
- understand float and clear
- understand the overflow property
- understand pseudo selectors and elements

## Steps

Each step has a link to what the website should look like after that step. Use that to help you know what is needed for that step.

### Step 1.

Let's create a header that is 80px in height, has a white background, a 1px black border, and 100% width. Instead of creating a style rule for the `<header>` element, let's give the `<header>` a class of `main-header` and create a CSS style rule for that class.

If you refresh the browser, you will notice that there is a little space on the left and right side of the headers border. This is because of some default margin on the body element. Lets create a css style rule for the `body` element and set the margin to 0.

Nice work! Now we have a header!

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    <header class="main-header"></header>
    ...
  </body>
</html>
```

```css
body {
  margin: 0;
}

...

.main-header {
  background-color: #ffffff;
  border-bottom: 1px solid black;
  height: 80px;
  width: 100%;
}

...
```

</details>

### Step 2.

In this step we will create an image banner to show what Gallo Pinto looks like. Instead of using the html `<img>` element, we will use the generic block-level `<div>` element and use the css `background-image` property to give it an imagee.

Below the `<header>`, add a `<div>` and give it a class `banner`. Then, create a CSS style rule for the `.banner` class that will set the `background-image` to `https://pushcodedev.s3.us-west-1.amazonaws.com/public_assets/costa-rican-traditional-meal-white-plate-wooden-table.jpg`, the `height` to `500px`, the `background-position` to `center`, and the `background-size` to `cover`. We want the background image position to be in the center and we want the background image to cover the entire space. This will make it so that even if the dimensions of the image aren't perfect for the size we need, it will resize the image to cover all the space and make sure that the image is centered in case edges get cut off.

Next, we will add the `favicon` for our website. Under the `<title>` element, use the `<link>` element to add our favicon. The image file for our favicon is located at https://icons.pushcode.dev/turtle.svg.

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    <header class="main-header"></header>
    <div class="banner"></div>
    ...
  </body>
</html>
```

```css
...

.banner {
  background-image: url("https://pushcodedev.s3.us-west-1.amazonaws.com/public_assets/costa-rican-traditional-meal-white-plate-wooden-table.jpg");
  background-position: center;
  background-size: cover;
  height: 500px;
}

...
```

</details>

### Step 3.

In this step, we will create the right side section of our layout. This section will contain an image of a sloth, show how many stars the receip has, a button to see the reviews (we will turn our current `See Reviews` link into this button), cook time info, and nutritional info. In this step we will just create the section and the `See Reviews` button.

We will use the semantic `<aside>` html element, since the content of this section is related to the content on the page, but is not the primary content (and will be on the side).

Look in your html file and find the link to the reviews section of the document. It should look like `<a href="#reviews">See Reviews</a>`. Wrap that link in an `<aside>` element.

Then, create a CSS rule for the `aside` element and set the `background-color` to `#027b7e`, a `border-top` of `1px solid black`, `padding` of `80px 32px 240px` (this means the top padding will be 80px, left and right padding of 32px and bottom padding of 240px), and a width of 400px;

If you refresh the browser, you should see a teal rectangle below the banner image, with the rest of the page content below it. How do we make the teal rectable go to the right side, with the rest of the content below it on the left? We will use the `float` CSS property. Add the declaration `float: right;` to our `aside` CSS rule.

Refresh the browser and it should be on the right side! Pretty cool, right?!

Now, we need to create the button for the `See Reviews` link (why can't we see the link right now....because the color of the text is the same color as the background!). First, we want to wrap the words `See Reviews` in a `<button>` element, and the `<button>` element should be a child of the `<a>` element. We will want to create a CSS rule for our button elements so they all have a similar style (in case we add more buttons later on). Add the following CSS rule for `button`:

```css
button {
  border-radius: 6px;
  border: none;
  cursor: pointer;
  height: 40px;
  padding: 0 16px;
}
```

Now, this button should have an orange/gold background, so we want to add a class to the `<button>` element for the `See Reviews` link. Let's have the class be `reviews-button`. Then in our CSS we can create a rule for our class `.reviews-button` that sets the `background-color` to `#f0a433`.

Go over to the browser and you should see the button! And when you click on it, it should take you to the reviews section of the document! You might notice that it takes you directly there with no scroll effect. To make it scroll to that section we can add `scroll-behavior: smooth;` to our universal `*` selector.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    <header class="main-header"></header>
    <div class="banner"></div>
    <aside>
      <a class="reviews-button" href="#reviews">See Reviews</a>
    </aside>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <p>...</p>
  </body>
</html>
```

```css
* {
  font-family: "Montserrat", sans-serif;
  scroll-behavior: smooth;
}

/* ...  */

aside {
  background-color: #027b7e;
  border-top: 1px solid;
  float: right;
  padding: 80px 32px 240px;
  width: 400px;
}

button {
  border-radius: 6px;
  border: none;
  cursor: pointer;
  height: 40px;
  padding: 0 16px;
}

/* ... */

.reviews-button {
  background-color: #f0a433;
}
```

</details>

### Step 4.

In this step we are going to add the 5 gold stars to both the side section and the `Reviews` heading. To add these stars we are going to use icons that are available for free via Font Awesome. Font Awesome has a ton of free and paid icons to choose from. Go to font awesomes website, sign up and follow the structions to create a kit and embed your kits code in the `<head>` of your document. If you don't want to create an account, you can also just add

```html
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.2/css/all.min.css"
  integrity="sha512-1sCRPdkRXhBV2PBLUdRb4tMg1w2YPf37qatUFeS7zlBy7jJI8Lf4VHwWfZZfpXtYSLy85pkm9GaYVYMfw5BC1A=="
  crossorigin="anonymous"
  referrerpolicy="no-referrer"
/>
```

in the `<head> ` of your document. Once we have access to Font Awesome, we can use any of
their free icons. Pretty cool!! So for the stars, we will use `<i class="fa-solid fa-star"></i>`.

Above the `<button>` to `See Reviews` and as a child of the `<a>` element, you will add a `<div>` element and give it a class of `stars`. Within the `<div>` you will add in five of the star icons `<i class="fa-solid fa-star"></i>`. Because all of this is within the `<a>` element, you can click on the starts or the button and it will take you to the reviews section.

Now, in the CSS file, add a rule for the class `.stars` and set the `color` to `#f0a433` and `margin-bottom` of `32px`. This is starting to look like it is supposed to. Now, you want to make it centered. Wrap the `<a>` element within a `<div>` and give the `<div>` a class of `rating-wrapper`. Then create a CSS rule for `.rating-wrapper` and set `text-align` to `center`.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    ...
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.2/css/all.min.css"
      integrity="sha512-1sCRPdkRXhBV2PBLUdRb4tMg1w2YPf37qatUFeS7zlBy7jJI8Lf4VHwWfZZfpXtYSLy85pkm9GaYVYMfw5BC1A=="
      crossorigin="anonymous"
      referrerpolicy="no-referrer"
    />
  </head>
  <body>
    <header class="main-header"></header>
    <div class="banner"></div>
    <aside>
      <div class="rating-wrapper">
        <a href="#reviews">
          <div class="stars">
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
          </div>
          <button class="reviews-button">See Reviews</button>
        </a>
      </div>
    </aside>
    ...
  </body>
</html>
```

```css
/* ...  */

.rating-wrapper {
  text-align: center;
}

/* ... */

.stars {
  color: #f0a433;
  margin-bottom: 32px;
}
```

</details>

### Step 2.

In this Step, we will create the different `headings` we need on the site. For the main title we will use an `<h1>` element, and within the opening and closing tags type `costa rican gallo pinto` in all lowercase (this is so we can format it later using CSS, just to get some practice). Let's add an `id` attribute on the opening `<h1>` tag with the value `main-title`. We will use this `id` later on the style our title.

<!-- TODO: add instructions -->

In this step we will create the cook time and servigs section.
Below the `<div>` with class `rating-wrapper`, you will add another `<div>` and give it a class of `cook-time-wrapper`. This `div` will group all of the elements for this section. Inside of the `<div class="cook-time-wrapper>`, add 4 `<div>` elements with class `row`. These will group the elements for each row (prep time, cook time, total time, and servings) in the section.
In each `<div>` with class `row`, add 2 `<span>` elements. the first with class `label` and the second with class `value`. Add the approprate text inside each span. For example, looking at the first row, the `label` span should have the content `Prep time` and the `value` span should have the content `10 min`. Look at the website example to see what to add for the other rows.

Now to style things with CSS. Add a rule for class `.cook-time-wrapper` and set the `padding` to `48px`. This will add a 48px padding between the border of the container (which we can't see) and the content of the container. Next, create a CSS rule for the class `.row` that is a child of `.cook-time-wrapper`. Use the CSS direct child selector to make sure you only target elements with class `row` that are direct children of an element with class `cook-time-wrapper`. Give this css rule 2 declarations: `color: #ffffff;` & `margin-bottom: 24px;`. Next, we want the label and value to be separated on the same line. Create a CSS rule that targets the class `.value` that is a direct child of the class `.row` that is a direct child of the class `.cook-time-wrapper`. Give this a rule the declaration: `float: right;`.

You can leave it like this, or as a stretch goal, try to add the icons to each of the rows in front of the label.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    ...
    <aside>
      <div class="rating-wrapper">
        <a href="#reviews">
          <div class="stars">
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
          </div>
          <button class="reviews-button">See Reviews</button>
        </a>
      </div>

      <div class="cook-time-wrapper">
        <div class="row">
          <i class="fa-solid fa-utensils"></i>
          <span class="label">Prep time</span>
          <span class="value">10 min</span>
        </div>
        <div class="row">
          <i class="fa-solid fa-fire-burner"></i>
          <span class="label">Cook time</span>
          <span class="value">20 min</span>
        </div>
        <div class="row">
          <i class="fa-solid fa-clock"></i>
          <span class="label">Total time</span>
          <span class="value">30 min</span>
        </div>
        <div class="row">
          <i class="fa-solid fa-bowl-food"></i>
          <span class="label">Servings</span>
          <span class="value">8</span>
        </div>
      </div>
    </aside>
    ...
  </body>
</html>
```

</details>

<details>

```css
.cook-time-wrapper {
  padding: 48px;
}

.cook-time-wrapper > .row {
  color: #ffffff;
  margin-bottom: 24px;
}

.cook-time-wrapper > .row > .value {
  float: right;
}

.cook-time-wrapper i {
  color: #f0a433;
  font-size: 24px;
  width: 40px;
}
```

</details>

### Step 6.

<!-- TODO: add instructions -->

In this step we will add the nutritional information section. There will be some similarites in this step with the last step.
First, under the `cook-time-wrapper` div, create a `<div>` and give it a class of `nutritional-info-wrapper`. This will be our grouping container for the nutritional info section. Inside this div, add a `<header>` and 4 `<div>` elements with class `row`.
In the header, add the text `Nutritional Info`. In each of the 4 `<div>` elements with class `row` add 2 `<span>` elements. the first with class `label` and the second with class `value` (just like we did in the previous step). Look at the website example to see what text should go in each of these spans. For example, looking at the first row, the `label` span should have `Fat` and the `value` span should have `3g`.

Time to style! Add a CSS rule for class `.nutritional-info-wrapper` and give it the following declataions: `background-color: #ffffff;`, `border-radius: 6px;`, `box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1), 2px 0px 8px rgba(0, 0, 0, 0.1);`, and `overflow: hidden;`. Watch the video for this step to understand why we want `overlow: hidden;` here.

Next, create a CSS rule that will target the `header` element that is a direct child of `.nutritional-info-wrapper`. Give it the following declarations: `background: #005b5d;`, `color: #ffffff;`, and `padding: 16px;`.

Next, add a CSS rule that will target the elements with class `.row` that are direct children of an element with class `.nutritional-info-wrapper` (we did something similar in the last step). Give this rule the following declaration: `padding: 8px 16px;`. This will give a padding-top and padding-bottom of 8px and a padding-left and padding-right of 16px;

Next, we want every other row to have a different background-color. Use the `nth-child` pseudo-class selector to set the `background-color` to `#fafafa` for every `odd` row. Make sure to target only the `row`s that are directo children of `.nutritional-info-wrapper`. This one might be a little more challenging, so try to think through how to do this on your own first, and then look at the video or solution if you get stuck.

Next (like in the last step) we want the label and value to be separated on the same row, with the label on the left, and the value on the right. Try to think through how to do this one on your own.

As a stetch goal, try to add the calculator icon in the header (hint: use font-awesome).

<details>
```html
<!DOCTYPE html>
<html lang="en">
  ...

  <body>
    ...
    <aside>
      <div class="rating-wrapper">
        <a href="#reviews">
          <div class="stars">
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
          </div>
          <button class="reviews-button">See Reviews</button>
        </a>
      </div>
      <div class="cook-time-wrapper">
        <div class="row">
          <i class="fa-solid fa-utensils"></i>
          <span class="label">Prep time</span>
          <span class="value">10 min</span>
        </div>
        <div class="row">
          <i class="fa-solid fa-fire-burner"></i>
          <span class="label">Cook time</span>
          <span class="value">20 min</span>
        </div>
        <div class="row">
          <i class="fa-solid fa-clock"></i>
          <span class="label">Total time</span>
          <span class="value">30 min</span>
        </div>
        <div class="row">
          <i class="fa-solid fa-bowl-food"></i>
          <span class="label">Servings</span>
          <span class="value">8</span>
        </div>
      </div>
      <div class="nutritional-info-wrapper">
        <header><i class="fa-solid fa-calculator"></i> Nutritional Info</header>
        <div class="nutritional-info">
          <div class="row">
            <span class="label">Fat</span>
            <span class="value">3g</span>
          </div>
          <div class="row">
            <span class="label">Carbohydrates</span>
            <span class="value">27g</span>
          </div>
          <div class="row">
            <span class="label">Protein</span>
            <span class="value">4g</span>
          </div>
          <div class="row">
            <span class="label">Calories</span>
            <span class="value">165Kcal</span>
          </div>
        </div>
      </div>
    </aside>
    ...
  </body>
</html>
```

</details>

<details>

```css
.nutritional-info-wrapper > .row {
  padding: 8px 16px;
}

.nutritional-info-wrapper > .row:nth-child(odd) {
  background-color: #fafafa;
}

.nutritional-info-wrapper > .row > .value {
  float: right;
}

.nutritional-info-wrapper {
  background-color: #ffffff;
  border-radius: 6px;
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1), 2px 0px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.nutritional-info-wrapper > header {
  background: #005b5d;
  color: #ffffff;
  padding: 16px;
}
```

</details>

### Step 7.

We are almost done with the `aside` section of our website! How cool is this. One thing we are missing is the image of the sloth. Let's add it.

As the first child element of the `<aside>` element, lets add an `<img>` element and give it an `href` attribute with the location of the sloth image and a class atrribute of `sleeping-sloth`.

Create a CSS rule for the class `.sleeping-sloth` and set the `height` to `240px`.

The last thing we want to do is make sure the the width of our `aside` element is what we really want it to be. We set the `width` to `400px` earlier, but if we open our dev tools and look at the true width, we see that it is `464px`. Why is this? It is because padding is being added to the width of the container. If you remember from the content videos, there is a property that we can use to make it so border and padding does not add onto the width and height of our elements. The property is `box-sizing` and we set it to `border-box`. I like to apply this declaration to all elements in every project. So let's add it to the universal selector.

That's it for the `<aside>` section! Awesome work!

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...

  <body>
    ...
    <aside>
      <img
        src="images/sloth_sleeping.svg"
        alt="sleeping sloth"
        class="sleeping-sloth"
      />
      ...
    </aside>
    ...
  </body>
</html>
```

</details>

<details>

```css
* {
  box-sizing: border-box;
}

.sleeping-sloth {
  height: 240px;
}
```

</details>

### Step 8.

In this step we will start working on the left hand side of the website, or what we would consider our "main" content.

Under the `<aside>` element in out html document, we have all of our main content (the `<h1>` element all the way down to the last `<p>` element). Let's wrap all of this inside a `<main>` element.

Now, lets create a CSS rule for our `main` element and give it the following declarations: `background-color: #fafafa;`, `border-top: 1px solid black;`, and `width: calc(100% - 400px);`

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...

  <body>
    <header class="main-header"></header>
    <div class="banner"></div>
    <aside>...</aside>
    <main>
      <h1 id="main-title">costa rican gallo pinto</h1>
      ...
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
    </main>
  </body>
</html>
```

</details>

<details>

```css
main {
  background-color: #fafafa;
  border-top: 1px solid black;
  width: calc(100% - 400px);
}
```

</details>

### Step 9.

In the step we will group the content into different sections. We will have an "about" section, an "ingredients" section, an "instructions" section, a "more recipes" section, and a "reviews" section. Lets use the `<section>` element to create these sections.

Wrap everything between, but not including `<h1 id="main-title">costa rican gallo pinto</h1>` and `<h2 class="section-title">Ingredients</h2>` in a `<section>` element and give the `section` a class `about-section`.

Next, starting with (and including) `<h2 class="section-title">Ingredients</h2>` and ending with (and not including) `<h2 class="section-title">Instructions</h2>` wrap this is a `<section>` element with class `ingredients-section`.

Next, starting with (and including) `<h2 class="section-title">Instructions</h2>` and ending with (and not inluding) `<h2 class="section-title">More Recipes</h2>` wrap this in a `<section>` element with class `instructions-section`. You may be noticing a pattern that we are creating sections and each section (except for the first one) has an `<h2>` heading element, and then the content of that section.

Next, wrap `<h2 class="section-title">More Recipes</h2>` in a `<section>` element with class `more-recipes-section`.

Finally, wrap `<h2 id="reviews">Reviews</h2>` and and all the reviews in a `<section>` element with class `reviews-section`.

If you refresh the browser, you will not see any difference, but the `<section>` elements help us describe the structure of our code usig semantic elements, and we can not target them to add style.

Lets create a CSS rule that will target `section` elements with the following declarations: `margin: 0 auto;` (this will center the sections), `margin-bottom: 32px;`, and `max-width: 800px;`.

As a stretch goal...try and add the font-awesome icons you see in the webiste for each of the section headers.

<details>

```html
<!DOCTYPE html>
<html lang="en">

...

<body>
  <header class="main-header"></header>
  <div class="banner"></div>
  <aside>
    ...
  </aside>
  <main>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <section class="about-section">
      <p>
        <i>
          <b>Gallo Pinto</b>
        </i>
        is a traditional Cental American dish and has a long history in both
        Nicaraguan and Costa Rican culture. In Costa Rica, this breakfast dish is
        usually served with a fried egg, fresh plantains,
        <i>homemade</i>
        tortillas, and a cup of Costa Rican coffee.
      </p>
      <p>
        Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto is typically made using the rice and
        beans
        that are leftover from the day before.
      </p>
      <p>
        Gallo Pinto translates to
        <q>spotted rooster</q>
        . The name is said to come from the speckeled appearance of the dish.
      </p>
      <p>
        Would you beleive me if I told you that Gallo Pinto is considered one of the healthiest breakfast meals in the
        world? It's true! Accoring to Mike Dunphy's list of
        <cite>
          <a href="https://time.com/4254125/healthy-international-breakfast/" target="_blank">
            10 Healthy International Breakfasts
          </a>
        </cite>
        :
      <blockquote>
        Black beans-and the heavy amounts of iron, zinc, potassium, thiamin, and folate inside-play a central role in
        breakfast here. Mixed with rice, spiced with cumin, pepper, and garlic, Gallo Pinto often comes with eggs on the
        side and a host of vitamin-rich tropical fruits like mango, pineapple, papaya, and plantains. The breakfast
        might
        have a lot to do with Costa Rica's "Blue Zone" designation, given to countries with long-living populations.
      </blockquote>
      </p>
      <p>
        You can feel good about making this for your friends and family, knowing
        that it is, not only delicious, but also nutricious!
      </p>
    </section>
    <section class="ingredients-section">
      <h2 class="section-title"><i class="fa-solid fa-carrot"></i> Ingredients</h2>
      <ul>
        <li>3 cups cooked white rice</li>
        <li>2 cups cooked black beans</li>
        <li>1/4 cup bean broth, chicken broth, or water</li>
        <li>
          1/4 cup
          <a href="https://www.fusioncraftiness.com/lizano-sauce-from-costa-rica/" target="_blank">
            salsa lizano
          </a>
        </li>
        <li>1 small yellow onion, diced</li>
        <li>1 red bell pepper, diced</li>
        <li>1/4 cup chopped cilantro</li>
        <li>1 tsp sea salt</li>
        <li>1 tbsp olive oil</li>
      </ul>
    </section>
    <section class="instructions-section">
      <h2 class="section-title"><i class="fa-solid fa-list-ol"></i> Instructions</h2>
      <ol>
        <li>
          Heat oil in a large skillet over medium heat. Saute the onion and pepper
          until the onion becomes translucent.
        </li>
        <li>add the beans, broth, cilantro, and salt to the skillet and toss</li>
        <li>add the salsa lizano</li>
        <li>
          add the cooked rice and toss until well combined and heated thoroughly
        </li>
      </ol>
    </section>
    <section class="more-recipes-section">
      <h2 class="section-title">More Recipes</h2>
    </section>
    <section class="reviews-section">
      <h2 id="reviews">Reviews
        <span class="stars">
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
        </span>
      </h2>
      <h3>Leave a review</h3>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
      <p>
        <span class="name">John Doe</span>
        <span class="date">October 28, 2022</span>
      </p>
      <p>
        This is my families favorite new recipe. I made this last night and
        everyone loved it! Even my pickiest kid devoured it!
      </p>
    </section>
  </main>
</body>

</html>
```

</details>
  
### Step 7.

<details>

```css
section {
  margin: 0 auto;
  margin-bottom: 32px;
  max-width: 800px;
}
```

</details>

### Step 10.

In this step we will style our `Ingredients` section. Create a CSS rule that will select our element with class `ingredients-section` and give it the following declarations: `background-color: #ffffff;`, `border-radius: 6px;` (round the corners), `height: 300px;`, `padding-right: 48px;`, and `padding: 24px;`.

We want the ingredients to be split into 2 columns, so let's split the ingredients into 2 separate un-ordered lists. the first one will have the first 5 ingredietns, and the 2nd one will have the rest of the ingredients.

Then, we can create a rule that will target the `ul` elements that are direct children of our element with class `ingredients-section` and give it `float: left;`.

Next, lets create a CSS rule that will give all of the `li` elements in our document a `padding` of `8px`.

One more thing. our `h2` elements have some default style that is causing some extra margin that we don't want. Let use a CSS rule to target our `h2` elements and set the `margin` to `0`.

That's it for the `Ingredients` section! Excellent work!

<details>

```html
...

<section class="ingredients-section">
  <h2 class="section-title"><i class="fa-solid fa-carrot"></i> Ingredients</h2>
  <ul>
    <li>3 cups cooked white rice</li>
    <li>2 cups cooked black beans</li>
    <li>1/4 cup bean broth, chicken broth, or water</li>
    <li>
      1/4 cup
      <a
        href="https://www.fusioncraftiness.com/lizano-sauce-from-costa-rica/"
        target="_blank"
      >
        salsa lizano
      </a>
    </li>
    <li>1 small yellow onion, diced</li>
  </ul>
  <ul>
    <li>1 red bell pepper, diced</li>
    <li>1/4 cup chopped cilantro</li>
    <li>1 tsp sea salt</li>
    <li>1 tbsp olive oil</li>
  </ul>
</section>

...
```

</details>

<details>

```css
h2 {
  margin: 0;
}

li {
  padding: 8px;
}

.ingredients-section {
  background-color: #ffffff;
  border-radius: 6px;
  height: 300px;
  padding-right: 48px;
  padding: 24px;
}

.ingredients-section > ul {
  float: left;
}
```

</details>

### Step 8.

In this step, we will link our CSS file to our HTML file. In the `<head>` of our html document, use the `<link>` element, to link our `style.css` file. Once you have done that, let's add some style rules in our `style.css` file for our `#main-title` id, `.section-title` class and `h1` and `h2` elements.

For the `#main-title`, we want the font weight to be `normal` (instead of the bold that h1 elements get by default). We want the text to be aligned in the center, and we want the first letter of each word to be capitalized.

For the `.section-title` elements, we want the color of the text to be `#027b7e`.

For `h1` elements, we want the font size to be `2.5rem`.

In this step we will work on the `More recipes section`. This section doesn't have any content in it yet (except the heading), so go take a look at the example website for this step to see what this sections should look like and what the content should be. You can see that the section has a white background, similar to the "Ingredients" section. But this section has a shadow around it to make it look like it is raised up a bit. You can also see that there are 6 images of recipes (okay, it's the same image for the current recipe, but this is just for practice, and I didn't want to have to deal with multiple image files) and when you hover over each recipe, it darkens a litte. lets take this one step at a time and build out this section.

First, let's create a CSS rule for the element with class `more-recipes-section`. Let give this rule a declaration for the shadow around the section `box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1), 2px 0px 8px rgba(0, 0, 0, 0.1);`, another declaration to give a padding of 24px on all sides `padding: 24px;`, a declaration to round the corners of the border `border-radius: 6px;` and a declaration so the background is white `background-color: #ffffff;`. Let's also give it a `height` of `516px`.

Next, let's add the 6 recipes. Under the `<h2>` for this section, add a `<div>` element with a class `recipes-wrapper`, and inside this `div` add 6 `<div>` elements with class `recipe`. Inside of the each `<div>` with class `recipe` and a child `<div>` with class `recipe-overlay`. The `recipe-overlay` will be used to make the image darker when we hover over it.

If you refresh the page, nothing will look different. We will use CSS rules to do the rest of the work!

Create a CSS rule for the elements with class `recipe` that are descendants of an element with class `more-recipes-section`. Use the `Descendant combinator` selector to do this. We will use this rule so give each `recipe` div a background-image, and make sure the image is centered and covers the area. We also want to round the corners, make sure the images are the same size, 3 to a row, with a little space between them, and have the mouse cursor be a pointer. Here is the CSS rule to make all that happen:

```css
.more-recipes-section .recipe {
  background-image: url("https://pushcodedev.s3.us-west-1.amazonaws.com/public_assets/costa-rican-traditional-meal-white-plate-wooden-table.jpg");
  background-position: center;
  background-size: cover;
  border-radius: 6px;
  cursor: pointer;
  float: left;
  height: 200px;
  margin: 8px;
  width: calc((100% / 3) - 16px);
}
```

Try to read over this rule to understand what each part is doing.

Next we want to work on the overlay part that will allow us to darken the image when our mouse hovers over it. The first thing we will do is add a CSS rule to make the div with class `recipe-overlay` have a dark, but transparent background. We can use the `rgba` color option for this. `rgba(0, 0, 0, 0.5);` means we want the red, green and blue values to be `0` which would make the color black, and then the `0.5` alpha value will make it 50% transparent. Here's the rule we want to create:

```css
.recipe-overlay {
  background-color: rgba(0, 0, 0, 0.5);
}
```

If we refresh, nothing changes. Let's, temporarily, give our `.recipe-overlay` rule and `height` and `width` of `100%`. If we refresh, we can see that the overlay is making the images darker. Pretty cool, right?! This isn't exactly what we want though. We only want the background to be dark if we hover over the image. There are many many ways we can accomplish this, and the option we will use here isn't necessarily the best, but it's what we can do based on what we have learned in this unit. Here's what we will do...remove the `height` and `width` declarations from our `.recipe-overlay` CSS rule. Then create a rule that uses the `:hover` psuedo selector on `.recipe` to set the `.recipe-overlay` width and height to `100%`. Those instructions are probably a bit confusing, so let me jsut show you what I mean:

```css
.recipe:hover > .recipe-overlay {
  width: 100%;
  height: 100%;
}
```

This rule says to target the elements with class `recipe-overlay` that are direct children of an element with class `recipe` when the mouse is hovered over it; and set the `width` and `height` to `100%`. It's okay if this is a little confusing right now. With more practice these types of selectors will make more sense. And now that you have this example, you can come back to it any time you need to do something similar.

K, one more thing do note....do you see how when you hover over the recipe image, the overlay is a square with shard corners instead of the rounded corners we have on the recipe iamge? This is because the overlay is going outide the border of our recipe container because of the width and height of 100%. We can fix this by adding `overflow: hidden;` to our CSS rule for our `recipe` class.

Well, that's it for the `More recipes` section! You are doing GREAT!!!

<details>

```html
...

<section class="more-recipes-section">
  <h2 class="section-title">More Recipes</h2>
  <div class="recipes-wrapper">
    <div class="recipe">
      <div class="recipe-overlay"></div>
    </div>
    <div class="recipe">
      <div class="recipe-overlay"></div>
    </div>
    <div class="recipe">
      <div class="recipe-overlay"></div>
    </div>
    <div class="recipe">
      <div class="recipe-overlay"></div>
    </div>
    <div class="recipe">
      <div class="recipe-overlay"></div>
    </div>
    <div class="recipe">
      <div class="recipe-overlay"></div>
    </div>
  </div>
</section>

...
```

</details>

<details>

```css
.more-recipes-section {
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1), 2px 0px 8px rgba(0, 0, 0, 0.1);
  padding: 24px;
  border-radius: 6px;
  background-color: #ffffff;
  height: 516px;
}

.more-recipes-section .recipe {
  background-image: url("https://pushcodedev.s3.us-west-1.amazonaws.com/public_assets/costa-rican-traditional-meal-white-plate-wooden-table.jpg");
  background-position: center;
  background-size: cover;
  border-radius: 6px;
  float: left;
  height: 200px;
  margin: 8px;
  overflow: hidden;
  width: calc((100% / 3) - 16px);
}

.recipe-overlay {
  background-color: rgba(0, 0, 0, 0.5);
}

.recipe:hover > .recipe-overlay {
  width: 100%;
  height: 100%;
}
```

</details>

### Step 9.

In this step we will style the `name` and `date` portion of a review.
Since we want the name and date on the same line, but we want the date styled differently than the name, let's wrap the name portion in a `<span>` and give it a `class` of `name`, and wrap the date portion in a `<span>` and give it a `class` of `date`.

Then, in our CSS file, let's create a rule for the class `name` and set the font size to `1.1rem` and the font weight to `600`.
Now, let's create a rule for the class `date` and set the font size to `0.75rem` and make it so the text is underlined (think about which css property controls this?)

<details>

## HTML file

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    ...
    <h2 id="reviews" class="section-title">Reviews</h2>
    <h3>Leave a review</h3>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>
      <span class="name">John Doe</span>
      <span class="date">October 28, 2022</span>
    </p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
  </body>
</html>
```

## CSS file

```css
h1 {
  font-size: 2.5rem;
}

h2 {
  font-size: 1.5rem;
  font-weight: 600;
}

#main-title {
  font-weight: normal;
  text-align: center;
  text-transform: capitalize;
}

.date {
  font-size: 0.75rem;
  text-decoration: underline;
}

.name {
  font-size: 1.1rem;
  font-weight: 600;
}

.section-title {
  color: #027b7e;
}
```

2 more steps to go! We are almost finished with this project!

In this step we are going to add our form fields for "adding" a new review. This form will not actually do anything since that would require being able to send data somewhere and have is persist somehow. That's outside of the scope of this course.

Under `<h3>Leave a review</h3>`, add a `<form>` element with a class `review-form`. Inside the form, add a `<label>` element with a `for` attribute with the value `name`. Between the opening and closign `<label>` tags, type `Name`.
Then, below this `<input>` element, add an `<input>` element with and `id` attribte with a value of `name`, and a `type` attribute of `text`. The `id="name"` will match with the `for="name"` on the `<label>` so if you click on the label, it will focus the cursor in the input field. Pretty cool!

Follow the same steps, but for the `email` field. The only difference is the values for the `for`, `id`, and `type` attributes should be `email`.

After the email, we want to have the comment section. Create a label for `Comment` just like you did for `Name` and `Email`, and the value for the `for` attribute will be `comment`. Then, instead of using an `<input>`, we will use a `<textarea>`. Give the `<textarea>` and `id` of `comment` to follow the same pattern we've used for the other form fields. You can also add `cols` and `rows` attributes to the `<textare>` to specify how many columns and rows you want. In my example, I add `rows="10"`.

Below the comment you will add a `<label>` for subscribing to an email list. This form element will be a checkbox. The label should have a `for` attribute of `subscribe`. Then below the label, add an `<input>` with `id="subscribe"` and `type="checkbox`

Below all of these form fields, add a `<button>` with text `Post Comment` between the opening and closing tags. Since we have already created a CSS rule for our `button` elements, it should already have a decent style :)

Now to style our form a little.

Let's create a CSS rule that will target all of our `input` and `textarea` elements, and give them a border of `1px solid #fafafa`, a `border-radius` of `6px`, `padding` of `8px`, `margin-bottom` of `16px`, and `width` of `100%`. This already looks better, but you might notice that the checkbox is on it's own line, and that is because the checkbox is also an `input` and we gave the inputs a width of `100%`. So let's create an CSS rule that will target all checkbox elements using the attribute selector, override some of these declarations. It will look like this:

```css
[type="checkbox"] {
  height: initial;
  width: initial;
}
```

Next, create a rule that just targets `input` elements, and sets the `height` to `40px`.

Let's also change the background color of our button to be `#027b7e` and the color of the text to be `#ffffff`. I want you to think through how you can do this to target this specific button. We don't want it to cause changes other buttons in the documents.

One suggestion is to add a class to the button that you could target. Another option is to creat a rule that targets a `button` that is a direct child of `review-form`. In my vidoe and in the solution below, I use the latter option.

<details>

```css
input,
textarea {
  border: 1px solid #fafafa;
  border-radius: 6px;
  margin-bottom: 16px;
  padding: 8px;
  width: 100%;
}

[type="checkbox"] {
  height: initial;
  width: initial;
}

.review-form > button {
  background-color: #027b7e;
  color: #ffffff;
}
```

</details>

### Step 10.

Look at the progress you have made on this website! Amazing work!! I know this is a big project, and is a lot of work. It will be good to have this project to look back to when you need to do similar things. It also touched on all (or almost all) of the concepts taught in this unit!

This is the final step. For this step, we are going to make it so the reviews are in a scrollable box. Wrap all of the reviews (all the p tags and spans with the name, date and text for the comment) in a `div` and give it a class of `scroll-box`. All of the reviews should be in this single `div` that has class `scroll-box`.

Next, create a CSS rule for `.scroll-box` and set the `height` to `400px`. If you refresh the browser, not much will look different. Add the declaration `overflow: hidden;` and you should see that the content is being cut off. It is no longer showing all of the reviews. This is because we set a height on `.scroll-box`, so any content that takes up more space than that (or `overflows` the space) is being `hidden`. Now, change `overflow: hidden;` to `overflow: auto`, and you will see that the context now scrolls! We could also use `overflow: scroll;` and it would make the content scroll as well. You will almost always want to use `auto` instead of `scroll`. `auto` will only add the scroll bar if the content is larger than the container. If the content is not larger, it will not show the scroll bar. `scroll` always shows the scroll bar no matter what.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...

  <body>
    <header class="main-header"></header>
    ...
    <main>
      ...
      <section class="reviews-section">
        <h2 id="reviews">
          Reviews
          <span class="stars">
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
          </span>
        </h2>
        <h3>Leave a review</h3>
        <form action="" class="review-form">
          <label for="name" class="required-field">Name</label>
          <input id="name" type="text" name="name" />
          <label for="email">Email</label>
          <input type="email" name="email" id="email" />
          <label for="comment" class="required-field">Comment</label>
          <textarea name="comment" id="comment" rows="10"></textarea>
          <label for="subscribe" class="required-field"
            >Subscribe to email list</label
          >
          <input id="subscribe" type="checkbox" />
          <button>Post Comment</button>
        </form>
        <div class="scroll-box">
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
          <p>
            <span class="name">John Doe</span>
            <span class="date">October 28, 2022</span>
          </p>
          <p>
            This is my families favorite new recipe. I made this last night and
            everyone loved it! Even my pickiest kid devoured it!
          </p>
        </div>
      </section>
    </main>
  </body>
</html>
```

</details>

<details>

```css
.scroll-box {
  height: 400px;
  overflow: auto;
}
```

</details>

YOU DID IT!!!!!! I hope that this project was a lot of fun for you. I KNOW it was a lot of work, and probably some frustration. And my bet it that it still doesn't all make sense. That's OK! It's all about practice. The more you practice and build things, the easier it will get. This was a big project with a lot of different parts. Hopefully with the guided videos and the solutions for each step, you were able to figure it out. Below is a full solution of the html and CSS files. It is very good practice to start reading through the code and trying to understand exactly what is going on.

## Solution

<details>

<summary>index.html</summary>

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Gallo Pinto</title>
  <link rel="shortcut icon" href="https://icons.pushcode.dev/turtle.svg" type="image/x-icon" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap"
    rel="stylesheet" />
  <script src="https://kit.fontawesome.com/3b0fd6b80e.js" crossorigin="anonymous"></script>
  <link rel="stylesheet" href="step_13.css" />
</head>

<body>
  <header class="main-header"></header>
  <div class="banner"></div>
  <aside>
    <img src="images/sloth_sleeping.svg" alt="sleeping sloth" class="sleeping-sloth" />
    <div class="rating-wrapper">
      <a href="#reviews">
        <div class="stars">
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
        </div>
        <button class="reviews-button">See Reviews</button>
      </a>
    </div>
    <div class="cook-time-wrapper">
      <div class="row">
        <i class="fa-solid fa-utensils"></i>
        <span class="label">Prep time</span>
        <span class="value">10 min</span>
      </div>
      <div class="row">
        <i class="fa-solid fa-fire-burner"></i>
        <span class="label">Cook time</span>
        <span class="value">20 min</span>
      </div>
      <div class="row">
        <i class="fa-solid fa-clock"></i>
        <span class="label">Total time</span>
        <span class="value">30 min</span>
      </div>
      <div class="row">
        <i class="fa-solid fa-bowl-food"></i>
        <span class="label">Servings</span>
        <span class="value">8</span>
      </div>
    </div>
    <div class="nutritional-info-wrapper">
      <header><i class="fa-solid fa-calculator"></i> Nutritional Info</header>
      <div class="row">
        <span class="label">Fat</span>
        <span class="value">3g</span>
      </div>
      <div class="row">
        <span class="label">Carbohydrates</span>
        <span class="value">27g</span>
      </div>
      <div class="row">
        <span class="label">Protein</span>
        <span class="value">4g</span>
      </div>
      <div class="row">
        <span class="label">Calories</span>
        <span class="value">165Kcal</span>
      </div>
    </div>
  </aside>
  <main>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <section class="about-section">
      <p>
        <i>
          <b>Gallo Pinto</b>
        </i>
        is a traditional Cental American dish and has a long history in both
        Nicaraguan and Costa Rican culture. In Costa Rica, this breakfast dish is
        usually served with a fried egg, fresh plantains,
        <i>homemade</i>
        tortillas, and a cup of Costa Rican coffee.
      </p>
      <p>
        Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto is typically made using the rice and
        beans
        that are leftover from the day before.
      </p>
      <p>
        Gallo Pinto translates to
        <q>spotted rooster</q>
        . The name is said to come from the speckeled appearance of the dish.
      </p>
      <p>
        Would you beleive me if I told you that Gallo Pinto is considered one of the healthiest breakfast meals in the
        world? It's true! Accoring to Mike Dunphy's list of
        <cite>
          <a href="https://time.com/4254125/healthy-international-breakfast/" target="_blank">
            10 Healthy International Breakfasts
          </a>
        </cite>
        :
      <blockquote>
        Black beans-and the heavy amounts of iron, zinc, potassium, thiamin, and folate inside-play a central role in
        breakfast here. Mixed with rice, spiced with cumin, pepper, and garlic, Gallo Pinto often comes with eggs on the
        side and a host of vitamin-rich tropical fruits like mango, pineapple, papaya, and plantains. The breakfast
        might
        have a lot to do with Costa Rica's "Blue Zone" designation, given to countries with long-living populations.
      </blockquote>
      </p>
      <p>
        You can feel good about making this for your friends and family, knowing
        that it is, not only delicious, but also nutricious!
      </p>
    </section>
    <section class="ingredients-section">
      <h2 class="section-title"><i class="fa-solid fa-carrot"></i> Ingredients</h2>
      <ul>
        <li>3 cups cooked white rice</li>
        <li>2 cups cooked black beans</li>
        <li>1/4 cup bean broth, chicken broth, or water</li>
        <li>
          1/4 cup
          <a href="https://www.fusioncraftiness.com/lizano-sauce-from-costa-rica/" target="_blank">
            salsa lizano
          </a>
        </li>
        <li>1 small yellow onion, diced</li>
      </ul>
      <ul>
        <li>1 red bell pepper, diced</li>
        <li>1/4 cup chopped cilantro</li>
        <li>1 tsp sea salt</li>
        <li>1 tbsp olive oil</li>
      </ul>
    </section>
    <section class="instructions-section">
      <h2 class="section-title"><i class="fa-solid fa-list-ol"></i> Instructions</h2>
      <ol>
        <li>
          Heat oil in a large skillet over medium heat. Saute the onion and pepper
          until the onion becomes translucent.
        </li>
        <li>add the beans, broth, cilantro, and salt to the skillet and toss</li>
        <li>add the salsa lizano</li>
        <li>
          add the cooked rice and toss until well combined and heated thoroughly
        </li>
      </ol>
    </section>
    <section class="more-recipes-section">
      <h2 class="section-title">More Recipes</h2>
      <div class="recipes-wrapper">
        <div class="recipe">
          <div class="recipe-overlay"></div>
        </div>
        <div class="recipe">
          <div class="recipe-overlay"></div>
        </div>
        <div class="recipe">
          <div class="recipe-overlay"></div>
        </div>
        <div class="recipe">
          <div class="recipe-overlay"></div>
        </div>
        <div class="recipe">
          <div class="recipe-overlay"></div>
        </div>
        <div class="recipe">
          <div class="recipe-overlay"></div>
        </div>
      </div>
    </section>
    <section class="reviews-section">
      <h2 id="reviews">Reviews
        <span class="stars">
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
        </span>
      </h2>
      <h3>Leave a review</h3>
      <form action="" class="review-form">
        <label for="name" class="required-field">Name</label>
        <input id="name" type="text" name="name" />
        <label for="email">Email</label>
        <input type="email" name="email" id="email" />
        <label for="comment" class="required-field">Comment</label>
        <textarea name="comment" id="comment" rows="10"></textarea>
        <label for="subscribe" class="required-field">Subscribe to email list</label>
        <input id="subscribe" type="checkbox" />
        <button>Post Comment</button>
      </form>
      <div class="scroll-box">
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
        <p>
          <span class="name">John Doe</span>
          <span class="date">October 28, 2022</span>
        </p>
        <p>
          This is my families favorite new recipe. I made this last night and
          everyone loved it! Even my pickiest kid devoured it!
        </p>
      </div>
    </section>
  </main>
</body>

</html>

```

</details>

<details>

<summary>index.css</summary>

```css
* {
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
  scroll-behavior: smooth;
}

body {
  margin: 0;
}

button {
  border-radius: 6px;
  border: none;
  cursor: pointer;
  height: 40px;
  padding: 0 16px;
}

a {
  color: #027b7e;
  text-decoration: none;
}

aside {
  background-color: #027b7e;
  border-top: 1px solid;
  float: right;
  padding: 80px 32px 240px;
  width: 400px;
}

h1 {
  font-size: 2.5rem;
}

h2 {
  font-size: 1.5rem;
  font-weight: 600;
  margin: 0;
}

input,
textarea {
  border: 1px solid #fafafa;
  border-radius: 6px;
  margin-bottom: 16px;
  padding: 8px;
  width: 100%;
}

input {
  height: 40px;
}

li {
  padding: 8px;
}

main {
  background-color: #fafafa;
  border-top: 1px solid black;
  width: calc(100% - 400px);
}

section {
  margin: 0 auto;
  margin-bottom: 32px;
  max-width: 800px;
}

[type="checkbox"] {
  height: initial;
  width: initial;
}

#main-title {
  font-weight: normal;
  text-align: center;
  text-transform: capitalize;
}

.banner {
  background-image: url("https://pushcodedev.s3.us-west-1.amazonaws.com/public_assets/costa-rican-traditional-meal-white-plate-wooden-table.jpg");
  background-position: center;
  background-size: cover;
  height: 500px;
}

.cook-time-wrapper {
  padding: 48px;
}

.cook-time-wrapper i {
  color: #f0a433;
  font-size: 24px;
  width: 40px;
}

.cook-time-wrapper > .row {
  color: #ffffff;
  margin-bottom: 24px;
}

.cook-time-wrapper > .row > .value {
  float: right;
}

.date {
  font-size: 0.75rem;
  text-decoration: underline;
}

.ingredients-section {
  background-color: #ffffff;
  border-radius: 6px;
  height: 300px;
  padding-right: 48px;
  padding: 24px;
}

.ingredients-section > ul {
  float: left;
}

.main-header {
  background-color: #ffffff;
  border-bottom: 1px solid black;
  height: 80px;
  width: 100%;
}

.more-recipes-section {
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1), 2px 0px 8px rgba(0, 0, 0, 0.1);
  padding: 24px;
  border-radius: 6px;
  background-color: #ffffff;
  height: 516px;
}

.more-recipes-section .recipe {
  background-image: url("https://pushcodedev.s3.us-west-1.amazonaws.com/public_assets/costa-rican-traditional-meal-white-plate-wooden-table.jpg");
  background-position: center;
  background-size: cover;
  border-radius: 6px;
  cursor: pointer;
  float: left;
  height: 200px;
  margin: 8px;
  overflow: hidden;
  width: calc((100% / 3) - 16px);
}

.recipe-overlay {
  background-color: rgba(0, 0, 0, 0.5);
}

.recipe:hover > .recipe-overlay {
  width: 100%;
  height: 100%;
}

.name {
  font-size: 1.1rem;
  font-weight: 600;
}

.nutritional-info-wrapper > .row {
  padding: 8px 16px;
}

.nutritional-info-wrapper > .row:nth-child(odd) {
  background-color: #fafafa;
}

.nutritional-info-wrapper > .row > .value {
  float: right;
}

.nutritional-info-wrapper {
  background-color: #ffffff;
  border-radius: 6px;
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1), 2px 0px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.nutritional-info-wrapper > header {
  background: #005b5d;
  color: #ffffff;
  padding: 16px;
}

.rating-wrapper {
  text-align: center;
}

.reviews-button {
  background-color: #f0a433;
}

.review-form > button {
  background-color: #027b7e;
  color: #ffffff;
}

.scroll-box {
  height: 400px;
  overflow: auto;
}

.section-title {
  color: #027b7e;
}

.sleeping-sloth {
  height: 240px;
}

.stars {
  color: #f0a433;
  margin-bottom: 32px;
}
```

</details>

## Copyright

© Push LLC, 2020. Unauthorized use and/or duplication of this material without express and written permission from Push, LLC is strictly prohibited.

<p align="center"><?xml version="1.0" encoding="UTF-8" standalone="no"?>
</p>

## Summary

Every web developer needs a good code editor where they can write their code! There are a lot of options to choose from, however, my personal favorite is VSCode. I highly suggest you also use VSCode during this course for consistency with the videos.

In this project, I will guide you through installing and setting up VSCode so you can start coding!

- Learn how to create an html file in VSCode
- Learn how to use the `html:5` VSCode snippet to create boilerplate html code
- Learn how to open an html file in your web browser
- Display text in the web browser
