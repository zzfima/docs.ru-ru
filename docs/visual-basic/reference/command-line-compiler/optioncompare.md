---
title: "/optioncompare | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optioncompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optioncompare - параметр компилятора [Visual Basic]"
  - "optioncompare - параметр компилятора [Visual Basic]"
  - "-optioncompare - параметр компилятора [Visual Basic]"
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /optioncompare
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает способ сравнения строк.  
  
## Синтаксис  
  
```  
/optioncompare:{binary | text}  
```  
  
## Заметки  
 Можно задать `/optioncompare` в одном из двух форматов: `/optioncompare:binary`, чтобы использовать сравнения двоичных строк, и `/optioncompare:text`, чтобы использовать сравнения текстовых строк.  По умолчанию компилятор использует `/optioncompare:binary`.  
  
 В ОС Microsoft Windows используемая кодовая страница определяет двоичный порядок сортировки.  Обычный порядок двоичной сортировки выглядит следующим образом:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Сравнение текстовых строк основано на порядке сортировки, который определяется языковыми стандартами системы и не зависит от регистра букв.  Обычный порядок текстовой сортировки выглядит следующим образом:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### Установка параметра "\/optioncompare" в интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Compile**.  
  
3.  Измените значение в поле **Option Strict**.  
  
### Установка параметра "\/optioncompare" программными средствами  
  
-   Дополнительные сведения см. в разделе [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## Пример  
 Следующий код компилирует P`rojFile.vb` и использует сравнения двоичных строк.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)