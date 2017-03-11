---
title: "/optionstrict | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optionstrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optionstrict - параметр компилятора [Visual Basic]"
  - "optionstrict - параметр компилятора [Visual Basic]"
  - "-optionstrict - параметр компилятора [Visual Basic]"
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /optionstrict
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Применяет семантику строгого типа для ограничения неявных преобразований типов.  
  
## Синтаксис  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Необязательный.  Опция `/optionstrict+` ограничивает неявное преобразование типов.  Значением по умолчанию для этой опции является `/optionstrict-`.  Опция `/optionstrict+` совпадает с `/optionstrict`.  Можно использовать обе формы для разрешающей семантики.  
  
 `custom`  
 Обязательный.  Предупреждать, если строгая семантика языка не соблюдается.  
  
## Заметки  
 Когда действует параметр `/optionstrict+`, тогда неявно могут выполняться только расширяемые типы преобразований.  Неявные преобразования сужающего типа, такие как назначение объекта типа `Decimal` целочисленному объекту типа, вызывают ошибку.  
  
 Чтобы создать предупреждения для неявных сужающих преобразований типа, используйте `/optionstrict:custom`.  Используйте `/nowarn:numberlist`, чтобы игнорировать отдельные предупреждения, и `/warnaserror:numberlist`, чтобы рассматривать отдельные предупреждения как ошибки.  
  
### Чтобы установить параметр \/optionstrict в интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** щелкните **Свойства**. Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Compile**.  
  
3.  Измените значение в поле **Option Strict**.  
  
### Чтобы установить параметр \/optionstrict программными средствами  
  
-   Дополнительные сведения см. в разделе [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## Пример  
 Следующий код компилирует `Test.vb` с помощью строгой семантики.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [\/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)