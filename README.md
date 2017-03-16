# Tradeship for Emacs
Emacs plugin to run [tradeship](https://github.com/karthikv/tradeship), which
automatically imports missing JS dependencies and removes unused ones.

## Installation
Ensure you have tradeship installed:

```sh
$ npm install -g tradeship
# or use yarn:
$ yarn global add tradeship
```

Install tradeship-emacs by adding `tradeship.el` in this repository to your load
path. Then, add the following to `~/.emacs`:

```emacs
(require 'tradeship)
```

## Usage
To run tradeship, you may either:

- Execute `M-x tradeship`
- To run on save, add the following to your `~/.emacs`:

  ```emacs
  (add-hook 'js-mode-hook
            (lambda () (add-hook 'before-save-hook 'tradeship-before-save))))
  ```
- To run using a keyboard shortcut (e.g. <kbd>ctrl</kbd> + <kbd>alt</kbd> +
  <kbd>i</kbd>), add the following to your `~/.emacs`:

  ```emacs
  (global-set-key (kbd "C-M-i") 'tradeship)
  ```

The first time tradeship runs in a project directory with many JavaScript files,
it'll take some time to parse and cache dependencies. Future runs will be much
faster.

## License
See the comments at the top of [tradeship.el](tradeship.el).
