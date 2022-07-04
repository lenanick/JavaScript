   
 ## Напишите валидационный скрипт используя функции 
```
   1. Скрипт должен на вход принимать строку.
   2. После проверки строки выводить в консоль сообщение где 
   будет конкретно написано, что не так в ведённой строке.
   3. Минимум 5 символов в строке
   4. Максимум 64 символа в строке
   5. В строке должны быть буквы
   6. Должна быть хотя бы одна буква в верхнем регистре
   7. Должна быть хотя бы одна цифра
   8. Должна быть хотя бы одна @
   9. Строка не должна быть пустой
   
  ``` 
   
   
   function stringValidation(str) {
   if (checkStringAsNotNull(str)) {
       console.log("Error, String is empty");
   }

   if (typeof (str) !== 'string') {
       console.log('The value is not String!');
   }
   if (str.length < 5) {
       console.log('The string must have a minimum 5 symbols!');
   }
   if (str.length > 64) {
       console.log('The string must have a maximum 64 symbols!');
   }

   checkStringHasLetters(str);
   checkStringHasLettersInUpperCase(str);
   checkStringHasAtSymbol(str);
   checkStringHasNumber(str);
   }

   function checkStringAsNotNull(str) {
   return (str = '' && str.length == 0)
   }

   function isLetter(str) {
   return (str >= 'a' && str <= 'z') || (str >= 'A' && str <= 'Z');
   }

   function isLetterInUpperCase(str) {
   return (str >= 'A' && str <= 'Z');
   }

   function isNumber(str) {
   return (str > 0 && str <= 9);
   }

   function checkStringHasLetters(str) {
   for (let index = 0; index < str.length; index++) {
       const charAtIndex = str[index];
       const result = isLetter(charAtIndex);
       if (result === true) {
           return;
       }
    }

   console.log('String must have minimum one letter!');
  }

   function checkStringHasLettersInUpperCase(str) {
   for (let index = 0; index < str.length; index++) {
       const charAtIndex = str[index];
       const result = isLetterInUpperCase(charAtIndex);
       if (result === true) {
           return;
       }
   }

   console.log('String must have minimum one upper letter!');
   }

   function checkStringHasNumber(str) {
   for (let index = 0; index < str.length; index++) {
       const charAtIndex = str[index];
       const result = isNumber(charAtIndex);
       if (result === true) {
           return;
       }
   }

   console.log('String must have minimum one number!');
   }

   function checkStringHasAtSymbol(str) {
   for (let index = 0; index < str.length; index++) {
       const charAtIndex = str[index];
       const result = charAtIndex === '@';
       if (result === true) {
           return;
       }
   }

   console.log('String must have a @ symbol!');
  }

   stringValidation('GOOD JOB');
