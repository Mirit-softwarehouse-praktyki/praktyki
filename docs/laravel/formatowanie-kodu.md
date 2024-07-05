---
title: "Laravel - Formatowanie kodu"
---

## Instalacja Laravel Pint (formatowanie plików *.php)

- komenda do instalacji: [Laravel Pint](https://laravel.com/docs/11.x/pint#installation)
- w VSCode można skonfigurować jego automatyczne wywoływanie przy zapisaniu pliku:
[automatically run Laravel Pint on file save in VSCode](https://stackoverflow.com/questions/76327911/how-to-automatically-run-laravel-pint-on-file-save-in-vscode)

## Formater VSCode do plików blade
- np. [Laravel Blade - amirmarmul](https://marketplace.visualstudio.com/items?itemName=amirmarmul.laravel-blade-vscode)
- konfiguracja jako domyślny formater w VSCode:
    - będąc w pliku *.blade.php* klikamy *Ctrl + Shift + P*
    - wpisujemy *Format Document With*
    - wybieramy *Configure Default Formatter*
    - wybieramy *Laravel Blade*
- alternatywa do pliku *settings.json* w VSCode wklejamy:
  ```
  "[blade]": {
    "editor.defaultFormatter": "amirmarmul.laravel-blade-vscode",
  }
  ```
- formatowanie pliku: *Ctrl + Shift + I*