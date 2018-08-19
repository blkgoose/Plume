# Plume
Lightweight SPA library

#### Hello World example

```html
<!DOCTYPE html>

<script src="https://cdn.rawgit.com/blkgoose/Plume/master/Plume.min.js"></script>
<script>
  Plume(model =>
    root([text("Hello World!")])
  )
</script>
```

#### Routing example
```html
<!DOCTYPE html>

<script src="https://cdn.rawgit.com/blkgoose/Plume/master/Plume.min.js"></script>
<script>
  Plume(model =>
      root([
        router(model, {
          "/fixed/1": _ =>
            root([text("fixed route #1")]),

          "/dynamic/:num": data =>
            root([text(`dynamic route [${data.num}]`)]),

          "*": _ =>
            root([h("404 PAGE NOT FOUND", 1)]),
        })
      ])
    )
</script>
```

The Plume function returns the model object of the app,
if the binding element isn't set (third parameter),
the function returns a Promise of the model.
