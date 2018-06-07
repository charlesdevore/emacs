;;; init.el -- Custom Emacs Configuration

;;; Author: Charles DeVore

;;; Commentary:

;;; Code:

(package-initialize)

(let ((default-directory "~/.emacs.d/"))
  (normal-top-level-add-subdirs-to-load-path))

(require 'install-packages)
(require 'better-defaults)

(setq inhibit-startup-message t
      linum-format "%4d \u2502 ")

(global-linum-mode t)

;; modify ibuffer-formats to set name column wider
(setq ibuffer-formats
      '((mark modified read-only " "
              (name 40 40 :left :elide) " " filename)
        (mark " "
              (name 16 -1) " " filename)))

(load-theme 'cyberpunk t)
(windmove-default-keybindings)
(defalias 'yes-or-no-p 'y-or-n-p)

(require 'magit)
(global-set-key (kbd "C-c g") 'magit-status)


(add-hook 'after-init-hook 'global-company-mode)

;; customize company-mode
(setq company-idle-delay 0)
(setq company-echo-delay 0)
(setq company-minimum-prefix-length 1)

(require 'development)



(setq py-shell-name "python3")

(defun comment-or-uncomment-region-or-line ()
    "Comment/uncomment the region or current line."
    (interactive)
    (let (beg end)
        (if (region-active-p)
            (setq beg (region-beginning) end (region-end))
            (setq beg (line-beginning-position) end (line-end-position)))
        (comment-or-uncomment-region beg end)))

(global-set-key (kbd "M-;") 'comment-or-uncomment-region-or-line)

;; Maximize the screen on startup
(add-to-list 'default-frame-alist '(fullscreen . maximized))

;;; init.el ends here
