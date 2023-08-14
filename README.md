Landslide themes
================

Themes for Landslide (https://github.com/adamzap/landslide)

Altered theming from https://github.com/Kaljurand/landslide-themes

Support for fenced code blocks and highlightjs.

To enable highlightjs syntax highlighting, simply use fenced code blocks like so:

````
```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}
```
````

Then invoke landslide with:

```sh
# Notice the `-x extra` to enable fenced code blocks
landslide <file.md> -t <path/to/simple> -x extra
```

Themes
------

  - __simple__: modification of the Landslide default theme
    - no gradient
    - cleaner font
    - improved bullet style
    - less round corners

Notes
-----

Some notes which might have nothing to do with the themes.

### Rearranging slides

The only Powerpoint feature that I like is being able to conveniently reorder slides.
Well, you can do the same in Vim+landslide, just give your slides meaningful titles
(this you need for the table of contents anyway) and use folding to reduce them to single lines,
i.e. add something like this to your `.vimrc`.

    function MarkdownLevel()
      let h = matchstr(getline(v:lnum), '^#\+')
    	if empty(h)
    		return "="
    	else
    		return ">" . len(h)
    	endif
    endfunction

    au BufEnter *.md setlocal foldexpr=MarkdownLevel()
    au BufEnter *.md setlocal foldmethod=expr

(The code originates from <http://stackoverflow.com/questions/3828606/vim-markdown-folding#comment16309004_4677454>.)

Toggle folds by `za`, reorder slides by reordeing lines in the usual way.
