### Important note

When going through this project, I noticed some issues with the `prettier` code formatter in VSCode when formatting html. Especially with formatting `<cite>`, `<a>`, and `<blockquote>` elements. In fact, the `<blockquote>` element completely prevented the formatter from formatting. Because of this, I switched over to using VSCode's html formatter. To do this, I opened the `command palette` (CMD + Shift + P on mac), and searched for `Open Settings (JSON)` and clicked on the option.

This is what my my settings.json file contains:

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

In our guided projects throughout this course, we will be creating a Gallo Pinto recipe website. With each unit, as you learn more HTML & CSS, we will add to our website to create a modern recipe site that is responsive on both web and mobile. You can view the final project at https://gallo-pinto.pushcode.dev/. Since this unit has not covered everything you need to know in order to build the final version of this website, you can go to https://gallo-pinto.pushcode.dev/intro to see what we will be building for this guided project.

This guided project is broken down into steps. Each step will have a link so you can see what you are building for that step, and a guided video so you can follow along with me. There are also solutions for each step in case you get stuck or have a typo you can't find and you are starting to get frustrated. Try and do as much as you can on your own, and use the videos and solutions for help when you get stuck.

Our goals for this guided project are:

## Goals

- create an html file
- create a css file
- link your css file to your html file
- create a title for the html document
- add a favicon
- Use heading and paragraph elements to add text to your site
- format the text using semantic elements and css style properties
- use the html <a> element to link to internal and external resources
- use the html <span> element to target portions of the text we want to style without breaking onto a new line.

## Steps

### Step 1.

create a project directory for this project and name it `gallo-pinto-recipe`. Open your `gallo-pinto-recipe` directory in VSCode. Inside your `gallo-pinto-recipe` directory, create `index.html` and `style.css` files by clicking on the `new file` icon in VSCode. Once those files are created, open the `index.html` file by clicking on it in the left pane of VSCode.

Next, we will add some basic html boilerplate and add a title for our website. In VSCode, start typing `html` and you should see some options appear. Click on the `html:5` option. Once the boilerplate is added, take some time to look over what was created for you. Now, Look for the `<title></title>` element and within the opening and closing tags, type `Gallo Pinto`.

Next, we will add the `favicon` for our website. Under the `<title>` element, use the `<link>` element to add our favicon. The image file for our favicon is located at https://icons.pushcode.dev/turtle.svg.

Once you have done this, open the `index.html` file in the browser (I suggest using Google Chrome). You should see the favicon and title in the tab for the website!!

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Gallo Pinto</title>
    <link
      rel="shortcut icon"
      href="https://icons.pushcode.dev/turtle.svg"
      type="image/x-icon"
    />
  </head>
  <body></body>
</html>
```

</details>

### Step 2.

In this Step, we will create the different `headings` we need on the site. For the main title we will use an `<h1>` element, and within the opening and closing tags type `costa rican gallo pinto` in all lowercase (this is so we can format it later using CSS, just to get some practice). Let's add an `id` attribute on the opening `<h1>` tag with the value `main-title`. We will use this `id` later on the style our title.

Below the `<h1>`, add an `<h2>` with the text `Ingredients` between the opening and closing tags. Then, add another `<h2>` with the text `Instructions`, an `<h2>` with the text `More Reciepes`, and a final `<h2>` with the text `Reviews`. Add a `class` attribute to all of the `<h2>` elements and give it a value of `section-title`. We will use this class to style our `<h2>` headings.

Below the `<h2>` for `Reviews`, add an `<h3>` heading with the text `Leave a review`.

If you refresh the browser tab for your website, you should see the heading tags!

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <h2 class="section-title">Ingredients</h2>
    <h2 class="section-title">Instructions</h2>
    <h2 class="section-title">More Recipes</h2>
    <h2 class="section-title">Reviews</h2>
    <h3>Leave a review</h3>
  </body>
</html>
```

</details>

### Step 3.

In this step, we will add the paragraphs that go under the main title. Use the `<p>` element for each of these five paragraphs:

```
Gallo Pinto is a traditional Cental American dish and has a long history
in both Nicaraguan and Costa Rican culture. In Costa Rica, this breakfast
dish is usually served with a fried egg, fresh plantains, homemade
tortillas, and a cup of Costa Rican coffee.
```

```
Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto
is typically made using the rice and beans that are leftover from the day
before.
```

```
Gallo Pinto translates to spotted rooster. The name is said to come from
the speckeled appearance of the dish.
```

```
Would you beleive me if I told you that Gallo Pinto is considered one of
the healthiest breakfast meals in the world? It's true! Accoring to Mike
Dunphy's list of 10 Healthy International Breakfasts: >Black beans—and the
heavy amounts of iron, zinc, potassium, thiamin, and folate inside—play a
central role in breakfast here. Mixed with rice, spiced with cumin,
pepper, and garlic, Gallo Pinto often comes with eggs on the side and a
host of vitamin-rich tropical fruits like mango, pineapple, papaya, and
plantains. The breakfast might have a lot to do with Costa Rica's "Blue
Zone" designation, given to countries with long-living populations.
```

```
You can feel good about making this for your friends and family, knowing
that it is, not only delicious, but also nutricious!
```

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <p>
      Gallo Pinto is a traditional Cental American dish and has a long history
      in both Nicaraguan and Costa Rican culture. In Costa Rica, this breakfast
      dish is usually served with a fried egg, fresh plantains, homemade
      tortillas, and a cup of Costa Rican coffee.
    </p>
    <p>
      Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto
      is typically made using the rice and beans that are leftover from the day
      before.
    </p>
    <p>
      Gallo Pinto translates to spotted rooster. The name is said to come from
      the speckeled appearance of the dish.
    </p>
    <p>
      Would you beleive me if I told you that Gallo Pinto is considered one of
      the healthiest breakfast meals in the world? It's true! Accoring to Mike
      Dunphy's list of 10 Healthy International Breakfasts: >Black beans—and the
      heavy amounts of iron, zinc, potassium, thiamin, and folate inside—play a
      central role in breakfast here. Mixed with rice, spiced with cumin,
      pepper, and garlic, Gallo Pinto often comes with eggs on the side and a
      host of vitamin-rich tropical fruits like mango, pineapple, papaya, and
      plantains. The breakfast might have a lot to do with Costa Rica's "Blue
      Zone" designation, given to countries with long-living populations.
    </p>
    <p>
      You can feel good about making this for your friends and family, knowing
      that it is, not only delicious, but also nutricious!
    </p>

    <h2 class="section-title">Ingredients</h2>
    <h2 class="section-title">Instructions</h2>
    <h2 class="section-title">More Recipes</h2>
    <h2 class="section-title">Reviews</h2>
    <h3>Leave a review</h3>
  </body>
</html>
```

</details>

### Step 4.

Now we will add the un-ordered list of ingredients under the `Ingredients` heading, and the ordered list of instructions under the `Instructions` heading. Remember that each list item in the lists, we need to use the `<li>` element.

Here is the list of ingredients:

3 cups cooked white rice
2 cups cooked black beans
1/4 cup bean broth, chicken broth, or water
1/4 cup salsa lizano
1 small yellow onion, diced
1 red bell pepper, diced
1/4 cup chopped cilantro
1 tsp sea salt
1 tbsp olive oil

and here is the list of instructions:

Heat oil in a large skillet over medium heat. Saute the onion and pepper until the onion becomes translucent.
add the beans, broth, cilantro, and salt to the skillet and toss
add the salsa lizano
add the cooked rice and toss until well combined and heated thoroughly

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Gallo Pinto</title>
    <link
      rel="shortcut icon"
      href="https://icons.pushcode.dev/turtle.svg"
      type="image/x-icon"
    />
  </head>
  <body>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <p>
      Gallo Pinto is a traditional Cental American dish and has a long history
      in both Nicaraguan and Costa Rican culture. In Costa Rica, this breakfast
      dish is usually served with a fried egg, fresh plantains, homemade
      tortillas, and a cup of Costa Rican coffee.
    </p>
    <p>
      Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto
      is typically made using the rice and beans that are leftover from the day
      before.
    </p>
    <p>
      Gallo Pinto translates to spotted rooster. The name is said to come from
      the speckeled appearance of the dish.
    </p>
    <p>
      Would you beleive me if I told you that Gallo Pinto is considered one of
      the healthiest breakfast meals in the world? It's true! Accoring to Mike
      Dunphy's list of 10 Healthy International Breakfasts: Black beans—and the
      heavy amounts of iron, zinc, potassium, thiamin, and folate inside—play a
      central role in breakfast here. Mixed with rice, spiced with cumin,
      pepper, and garlic, Gallo Pinto often comes with eggs on the side and a
      host of vitamin-rich tropical fruits like mango, pineapple, papaya, and
      plantains. The breakfast might have a lot to do with Costa Rica's "Blue
      Zone" designation, given to countries with long-living populations.
    </p>
    <p>
      You can feel good about making this for your friends and family, knowing
      that it is, not only delicious, but also nutricious!
    </p>

    <h2 class="section-title">Ingredients</h2>
    <ul>
      <li>3 cups cooked white rice</li>
      <li>2 cups cooked black beans</li>
      <li>1/4 cup bean broth, chicken broth, or water</li>
      <li>1/4 cup salsa lizano</li>
      <li>1 small yellow onion, diced</li>
      <li>1 red bell pepper, diced</li>
      <li>1/4 cup chopped cilantro</li>
      <li>1 tsp sea salt</li>
      <li>1 tbsp olive oil</li>
    </ul>
    <h2 class="section-title">Instructions</h2>
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
    <h2 class="section-title">More Recipes</h2>
    <h2 class="section-title">Reviews</h2>
    <h3>Leave a review</h3>
  </body>
</html>
```

</details>

### Step 5.

In this step we will add some formatting to some of the words in our text. The first paragraph starts with `Gallo Pinto is a traditional...`. We want to make `Gallo Pinto` italic and bold so that it stands out.

Also in that first paragraph, let's stress emphasis to the word `homemade` since homemade tortillas are better than store bought!

In the 3rd paragraph we have `Gallo Pinto translates to spotted rooster`. Let's wrap `spotted rooster` in quotes (using the html `<q>` element, NOT by typing qutation marks in the text) since it is a translation.

In the 4th paragraph were we have `Accoring to Mike Dunphy's list of 10 Healthy International Breakfasts`, let's wrap `10 Healthy International Breakfasts` in a `<cite>` element since it is the title of an article written by Mike Dunphy. Technically, the title of an article should be wrapped in quotes, and titles of books or movies should be in italics, but this is just for practice, and we already used quotes, so just go with it :)

Also in the 4th paragraph, all fo the text following `Accoring to Mike Dunphy's list of 10 Healthy International Breakfasts:` is a quote from his articel. And since it is a long quote. Let's wrap it in a `<blockquote>` element.

That should be good for formatting the text for now :)

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Gallo Pinto</title>
    <link
      rel="shortcut icon"
      href="https://icons.pushcode.dev/turtle.svg"
      type="image/x-icon"
    />
  </head>
  <body>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <p>
      <i><b>Gallo Pinto</b></i> is a traditional Cental American dish and has a
      long history in both Nicaraguan and Costa Rican culture. In Costa Rica,
      this breakfast dish is usually served with a fried egg, fresh plantains,
      <i>homemade</i> tortillas, and a cup of Costa Rican coffee.
    </p>
    <p>
      Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto
      is typically made using the rice and beans that are leftover from the day
      before.
    </p>
    <p>
      Gallo Pinto translates to <q>spotted rooster</q>. The name is said to come
      from the speckeled appearance of the dish.
    </p>
    <p>
      Would you beleive me if I told you that Gallo Pinto is considered one of
      the healthiest breakfast meals in the world? It's true! Accoring to Mike
      Dunphy's list of <cite>10 Healthy International Breakfasts</cite>:
      <blockquote>
        beans—and the heavy amounts of iron, zinc, potassium, thiamin, and folate
        inside—play a central role in breakfast here. Mixed with rice, spiced with
        cumin, pepper, and garlic, Gallo Pinto often comes with eggs on the side
        and a host of vitamin-rich tropical fruits like mango, pineapple, papaya,
        and plantains. The breakfast might have a lot to do with Costa Rica's "Blue
        Zone" designation, given to countries with long-living populations.
      </blockquote>
    </p>
    <p>
      You can feel good about making this for your friends and family, knowing
      that it is, not only delicious, but also nutricious!
    </p>

    <h2 class="section-title">Ingredients</h2>
    <ul>
      <li>3 cups cooked white rice</li>
      <li>2 cups cooked black beans</li>
      <li>1/4 cup bean broth, chicken broth, or water</li>
      <li>1/4 cup salsa lizano</li>
      <li>1 small yellow onion, diced</li>
      <li>1 red bell pepper, diced</li>
      <li>1/4 cup chopped cilantro</li>
      <li>1 tsp sea salt</li>
      <li>1 tbsp olive oil</li>
    </ul>
    <h2>Instructions</h2>
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
    <h2 class="section-title">More Recipes</h2>
    <h2 class="section-title">Reviews</h2>
    <h3>Leave a review</h3>
  </body>
</html>
```

</details>

### Step 6.

In this step lets add some reviews under `Leave a review`. Each review will have a `name` for the person who left the review, a `date` that they left the review, and the review itself. We want the name and date to be on the same line next to each other, and the text for the review to be below the name and the date. Refer to the link for this step to see what it should look like.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    ...
  </head>
  <body>
    ...
    <h2 class="section-title">Reviews</h2>
    <h3>Leave a review</h3>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
  </body>
</html>
```

</details>

### Step 7.

Let's add a couple of links to our documents. In the ingredients list where we have `1/4 cup salsa lizano`, let's link `salsa lizano` to a recipe for making salsa lizano. Here's a recipe you can use: https://www.fusioncraftiness.com/lizano-sauce-from-costa-rica/. If that link no longer works, just search for a recipe for salsa lizano and copy the url. Use the `<a>` tag to create a hyperlink for `salsa lizano` to link to that website. We want the link to open in a new tab.

Another hyper link we want to create is for Mike Dunphy's list of `10 Healthy International Breakfasts`. Here's the link for the article: https://time.com/4254125/healthy-international-breakfast/. Using the `<a>` element, create a hyperlink that will open the article in a new tab.

After that, at the top of the document, above the `<h1>` element, use an `<a>` element to create a link that says `See Reviews` and links internally to the `Reviews` section. To do this, we need to add an `id` to our `<h2>` opening tag for `reviews`. Set the value of the `id` to `reviews`. Then in the opening tag of the `<a>` element at the top of the document, set the `href` attribute to `#reviews`. the `#` symbol, says that we want to scroll to the element in the document that has the `id` of that value.

Check out the link for this step to see what this should look like and how it should behave when you click on the links.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    <a href="#reviews">See Reviews</a>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <p>
      <i><b>Gallo Pinto</b></i> is a traditional Cental American dish and has a
      long history in both Nicaraguan and Costa Rican culture. In Costa Rica,
      this breakfast dish is usually served with a fried egg, fresh plantains,
      <i>homemade</i> tortillas, and a cup of Costa Rican coffee.
    </p>
    <p>
      Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto
      is typically made using the rice and beans that are leftover from the day
      before.
    </p>
    <p>
      Gallo Pinto translates to <q>spotted rooster</q>. The name is said to come
      from the speckeled appearance of the dish.
    </p>
    <p>
      Would you beleive me if I told you that Gallo Pinto is considered one of
      the healthiest breakfast meals in the world? It's true! Accoring to Mike
      Dunphy's list of <cite><a href="https://time.com/4254125/healthy-international-breakfast/" target="_blank">10 Healthy International Breakfasts</a></cite>:
      <blockquote>
        beans—and the heavy amounts of iron, zinc, potassium, thiamin, and folate
        inside—play a central role in breakfast here. Mixed with rice, spiced with
        cumin, pepper, and garlic, Gallo Pinto often comes with eggs on the side
        and a host of vitamin-rich tropical fruits like mango, pineapple, papaya,
        and plantains. The breakfast might have a lot to do with Costa Rica's "Blue
        Zone" designation, given to countries with long-living populations.
      </blockquote>
    </p>
    <p>
      You can feel good about making this for your friends and family, knowing
      that it is, not only delicious, but also nutricious!
    </p>

    <h2 class="section-title">Ingredients</h2>
    <ul>
      <li>3 cups cooked white rice</li>
      <li>2 cups cooked black beans</li>
      <li>1/4 cup bean broth, chicken broth, or water</li>
      <li>1/4 cup <a href="https://www.fusioncraftiness.com/lizano-sauce-from-costa-rica/" target="_blank">salsa lizano</a></li>
      <li>1 small yellow onion, diced</li>
      <li>1 red bell pepper, diced</li>
      <li>1/4 cup chopped cilantro</li>
      <li>1 tsp sea salt</li>
      <li>1 tbsp olive oil</li>
    </ul>
    <h2 class="section-title">Instructions</h2>
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
    <h2 class="section-title">More Recipes</h2>
    <h2 id="reviews">Reviews</h2>
    <h3>Leave a review</h3>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p>John Doe October 28, 2022</p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
  </body>
</html>
```

</details>

### Step 8.

In this step, we will link our CSS file to our HTML file. In the `<head>` of our html document, use the `<link>` element, to link our `style.css` file. Once you have done that, let's add some style rules in our `style.css` file for our `#main-title` id, `.section-title` class and `h1` and `h2` elements.

For the `#main-title`, we want the font weight to be `normal` (instead of the bold that h1 elements get by default). We want the text to be aligned in the center, and we want the first letter of each word to be capitalized.

For the `.section-title` elements, we want the color of the text to be `#027b7e`.

For `h1` elements, we want the font size to be `2.5rem`.

For `h2` elements, we want the font size to be `1.5rem`, and we want the font weight to be `600`.

Try and create these rules on your own before looking at the solution or the guided video!

When you refresh the browser tab, you should see the style for your heading tags!

<details>

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

.section-title {
  color: #027b7e;
}
```

</details>

### Step 9.

In this step we will style the `name` and `date` portion of a review.
Since we want the name and date on the same line, but we want the date styled differently than the name, let's wrap the name portion in a `<span>` and give it a `class` of `name`, and wrap the date portion in a `<span>` and give it a `class` of `date`.

Then, in our CSS file, let's create a rule for the class `name` and set the font size to `1.1rem` and the font weight to `600`.
Now, let's create a rule for the class `date` and set the font size to `0.75rem` and make it so the text is underlined (think about which css property controls this?)

<details>

```html
<!DOCTYPE html>
<html lang="en">
  ...
  <body>
    ...
    <h2 id="reviews">Reviews</h2>
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

</details>

<details>

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

</details>

### Step 10.

Our site is getting really close to looking like it is supposed to. In this step, we want to style our `<a>` elements, cause we don't want to use the default styles.

In our CSS file, let's create a CSS rule for `a` elements and set the color to be `#027b7e`, and make it so the text is not underlined (I want you to think how to do this one).

<details>

```css
a {
  color: #027b7e;
  text-decoration: none;
}
...
```

</details>

### Step 11.

This is the final step for this project! We are almost there :)
In this step we want to set the `font-family` for our document. We will use google fonts to add a more professional looking font.
Go to `fonts.google.com` and look for `Montserrat` and click on it. Click on the `+` icon to add all of the different thicknesses and styles.
After you have selected all of the styles, copy the `<link>` code and paste it in the `<head>` of your html document.
Then, copy the css rule, and use the `universal selector` to set the `font-family` for all elements in our document.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Gallo Pinto</title>
    <link
      rel="shortcut icon"
      href="https://icons.pushcode.dev/turtle.svg"
      type="image/x-icon"
    />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="step_11.css" />
  </head>
  <body>
    ...
  </body>
</html>
```

</details>

<details>

```css
* {
  font-family: "Montserrat", sans-serif;
}
...
```

</details>

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
    <link
      rel="shortcut icon"
      href="https://icons.pushcode.dev/turtle.svg"
      type="image/x-icon"
    />
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="step_11.css">
  </head>
  <body>
    <a href="#reviews">See Reviews</a>
    <h1 id="main-title">costa rican gallo pinto</h1>
    <p>
      <i><b>Gallo Pinto</b></i> is a traditional Cental American dish and has a
      long history in both Nicaraguan and Costa Rican culture. In Costa Rica,
      this breakfast dish is usually served with a fried egg, fresh plantains,
      <i>homemade</i> tortillas, and a cup of Costa Rican coffee.
    </p>
    <p>
      Rice and black beans are staples in the Costa Rican diet, and Gallo Pinto
      is typically made using the rice and beans that are leftover from the day
      before.
    </p>
    <p>
      Gallo Pinto translates to <q>spotted rooster</q>. The name is said to come
      from the speckeled appearance of the dish.
    </p>
    <p>
      Would you beleive me if I told you that Gallo Pinto is considered one of
      the healthiest breakfast meals in the world? It's true! Accoring to Mike
      Dunphy's list of <cite><a href="https://time.com/4254125/healthy-international-breakfast/" target="_blank">10 Healthy International Breakfasts</a></cite>:
      <blockquote>
        Black beans—and the heavy amounts of iron, zinc, potassium, thiamin, and folate
        inside—play a central role in breakfast here. Mixed with rice, spiced with
        cumin, pepper, and garlic, Gallo Pinto often comes with eggs on the side
        and a host of vitamin-rich tropical fruits like mango, pineapple, papaya,
        and plantains. The breakfast might have a lot to do with Costa Rica's "Blue
        Zone" designation, given to countries with long-living populations.
      </blockquote>
    </p>
    <p>
      You can feel good about making this for your friends and family, knowing
      that it is, not only delicious, but also nutricious!
    </p>

    <h2 class="section-title">Ingredients</h2>
    <ul>
      <li>3 cups cooked white rice</li>
      <li>2 cups cooked black beans</li>
      <li>1/4 cup bean broth, chicken broth, or water</li>
      <li>1/4 cup <a href="https://www.fusioncraftiness.com/lizano-sauce-from-costa-rica/" target="_blank">salsa lizano</a></li>
      <li>1 small yellow onion, diced</li>
      <li>1 red bell pepper, diced</li>
      <li>1/4 cup chopped cilantro</li>
      <li>1 tsp sea salt</li>
      <li>1 tbsp olive oil</li>
    </ul>
    <h2 class="section-title">Instructions</h2>
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
    <h2 class="section-title">More Recipes</h2>
    <h2 id="reviews">Reviews</h2>
    <h3>Leave a review</h3>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
    <p><span class="name">John Doe</span> <span class="date">October 28, 2022</span></p>
    <p>
      This is my families favorite new recipe. I made this last night and
      everyone loved it! Even my pickiest kid devoured it!
    </p>
  </body>
</html>

```

</details>

<details>

<summary>index.css</summary>

```css
* {
  font-family: "Montserrat", sans-serif;
}

a {
  color: #027b7e;
  text-decoration: none;
}

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

</details>

## Copyright

© Push LLC, 2020. Unauthorized use and/or duplication of this material without express and written permission from Push, LLC is strictly prohibited.

<p align="center"><?xml version="1.0" encoding="UTF-8" standalone="no"?>
</p>
