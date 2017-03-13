---
title: "Оператор Option Explicit (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Explicit"
  - "vb.OptionExplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объявление переменных, explicit"
  - "Explicit - ключевое слово"
  - "явное объявление переменных"
  - "принудительное объявление переменных в операторе Option Explicit"
  - "Option Explicit - оператор"
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор Option Explicit (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Требует явного объявления всех переменных в файле или позволяет неявного объявления переменных.  
  
## Синтаксис  
  
```  
Option Explicit { On | Off }  
```  
  
## Части  
 `On`  
 Необязательный.  Включает проверку `Option Explicit`.  Если параметры `On` и `Off` не указаны, то по умолчанию используется параметр `On`.  
  
 `Off`  
 Необязательный.  Отключает проверку `Option Explicit`.  
  
## Заметки  
 При использовании в файле `Option Explicit On` или `Option Explicit` необходимо явно объявлять все переменные с помощью инструкций `Dim` или `ReDim`.  Если попытаться использовать имя необъявленной переменной, то возникает ошибка времени компиляции.  Оператор `Option Explicit Off` разрешает неявное объявление переменных.  
  
 При использовании оператор `Option Explicit` должен находиться перед всеми остальными операторами исходного кода.  
  
> [!NOTE]
>  Установка значения параметра `Option Explicit` равным `Off` как правило не является хорошей практикой.  Могла произойти ошибка в имя переменной в одной или нескольких местах, что приведет к непредвиденным результатам при запуске программы.  
  
## При отсутствии оператора Option Explicit  
 Если исходный код не содержит оператор`Option Explicit` , используется параметр**Option Explicit** [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) .  Если используется компилятор в командной строке, то используется параметр компилятора [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md).  
  
#### Установка режиме Option Explicit через интерфейс IDE  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Перейдите на вкладку **Compile**.  
  
3.  Задайте значение в поле **Option Explicit**.  
  
 При создании нового проекта параметр **Option Explicit** на вкладке**компилировать** устанавливается для параметра**Option Explicit** в диалоговом окне **умолчания VB**.  Чтобы открыть диалоговое окно **Параметры Visual Basic по умолчанию**, в меню **Сервис** выберите команду **Параметры**.  В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры VB по умолчанию**.  Исходный параметр по умолчанию в**Параметры VB по умолчанию** \- `On`.  
  
#### Установка режима Option Explicit из командной строки  
  
-   Включите параметр компилятора [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) в команду **vbc**.  
  
## Пример  
 В этом примере показано применение оператора `Option Explicit` для включения обязательного объявления всех переменных.  Попытка использования необъявленных переменных приводит к появлению ошибки времени компиляции.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)