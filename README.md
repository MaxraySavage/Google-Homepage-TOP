# Google-Homepage-TOP
A clone of the google homepage. First HTML + CSS project from The Odin Project.

## Goals
Gain familiarity with HTML, CSS, developer tools. 

## Process
I experimented with the original Google page and investigated its behavior, taking notes in [notes.md].

Then I built a very rough html structure to mirror the original page that looked something like

* Header
* Logo
* Search Form
* Footer

I set different background colors for each element and played around with getting them to sit something like the original page.

Then I refined the rough draft by adding actual elements to the header, search form and footer and adjusting flex-box parameters to get the behavior I wanted.

Once I got pretty close to the Google home page design, I began using developer's tools to inspect elements on the original page to get actual color values and troubleshoot certain flexbox behaviors.

## Interesting Points
The two parts of this project I enjoyed the most were getting the footer to behave the way I wanted it to on page resize as well as getting the google logo to move correctly with page resizing. 

### Footer Behavior
I ended up using two media queries to manually adjust the order of flexbox elements in the footer so that they would stack with the desired bahvior.

That looked like this 

```CSS
@media all and (max-width: 1300px) {
    footer {
        flex-wrap: wrap-reverse;
    }
    footer .center-links {
        order: 5;
    }

}

@media all and (max-width: 600px) {

    footer .left-links {
        order: 4;
        width: 100%;
        justify-content: space-evenly;
    }

    footer .right-links {
        width: 100%;
        justify-content: space-evenly;
    }

}
```

### Logo Behavior
I wanted the Google logo to pull away from the header but only after the page expanded beyond a particular height. I placed a div above the Google logo itself that would expand its top margin with the CSS function ```max()```.

```css
.logo-top-space {
    margin-top: max(100vh - 982px, 0px);
}
```

## Lessons Learned
Thining about how I would attack this differently now, I think I would be better able to decide how each flexbox should justify and align content from the beginning rather than throwing it all together and then adjusting until I got to the desired behavior. There are some aspects fo my CSS which may conflict or not be the most inteligible or simple way to get to the desired outcome. I now feel much more comfortable with flexboxes and css so I would say this project was a complete success!