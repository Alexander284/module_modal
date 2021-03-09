# module_modal
1. Для использования модуля необходимо установить npm пакеты:
   - npm init -y
   - npm install webpack webpack-cli --save-dev

2. Важно обращать внимания на пути в файле webpack.config.js

3. Так же в проекте должен лежать файл script.js с содержимым:
```javascript
   "use strict";
   
   import modal from './modal';
   import {openWindowModal} from './modules/modal';

   
   window.addEventListener('DOMContentLoaded', () =>{
      
	    const modalTimerId = setTimeout(() => openWindowModal('.modal', modalTimerId), 50000);
		  
		modal('[data-modal]', '.modal', modalTimerId);

   });
```
  - В файле modal.js в главную функцию передаются 3 аргумента:
	+ triggerSelector - '[data-modal]' (кнапка для вызова модального окна);
	+ modalSelector - '.modal' (само модальное окно);
	+ modalTimerId (такймер для запуска модального окна);

4. Чтобы собрать с помощью webpack, использовать команду: npx webpack.
