# playground4quartobook

Playground for a quarto book website in github page.

## How to use it

Run in the terminal:

```
git clone https://github.com/jrosell/playground4quartobook
cd playground4quartobook/src
make
```

Open http://127.0.0.1:8080 in your browser. It should show web directory contents.

You can edit the .qmd files in the src folder and rerender all the project

```
make
```

Or you can work on your drafts on src/_book directory. For example:

```
make partial FILE=chapter4-draft.qmd
```

