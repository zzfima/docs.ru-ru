---
title: "Условные обозначения и соглашения о коде (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b6db5c223b0548e308b49a686cff72eaaf8da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Условные обозначения и соглашения о коде (Visual Basic)
Документации Visual Basic используются следующие условные обозначения и соглашения о написании кода.  
  
## <a name="typographic-conventions"></a>Обозначения  
  
|Пример|Описание|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Зарезервированные слова языка и члены среды выполнения имеют начальные прописные буквы и форматируются как показано в следующем примере.|  
|**SmallProject**, **ButtonCollection**|Слова и фразы, будет предложено ввести форматируются как показано в следующем примере.|  
|[Оператор Module](../../visual-basic/language-reference/statements/module-statement.md)|Ссылки, которые можно щелкнуть для перехода на другую страницу справки, форматируются как показано в следующем примере.|  
|*Объект*, *variableName*,`argumentList`|Заполнители для сведений, предоставляемых пользователем, форматируются как показано в следующем примере.|  
|[Теней] [ *expressionList* ]|В синтаксисе необязательные элементы заключены в квадратные скобки.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|Если необходимо сделать выбор между двумя или несколькими элементами, элементы в синтаксисе заключены в фигурные скобки и разделяются вертикальной чертой.<br /><br /> Необходимо выбрать один и только один из элементов.|  
|[ `Protected` &#124; `Friend` ]|Если у вас есть возможность выбрать между двумя или более элементов, элементы в синтаксисе заключаются в квадратные скобки и разделяются вертикальной чертой.<br /><br /> Можно выбрать любое сочетание элементов или ни один элемент.|  
|[{ `ByVal` &#124; `ByRef` }]|В синтаксисе когда можно выбрать не более одного элемента, но можно также опустить элементы полностью, элементы заключаются в квадратные скобки заключены в фигурные скобки и разделяются вертикальной чертой.|  
|*имя пользователя*1, *memberName*2, *memberName*3|Несколько экземпляров одной позиции отличаются тем, индексов, как показано в примере.|  
|*Имя_члена1*<br /><br /> ...<br /><br /> *memberNameN*|В синтаксисе многоточие (...) используется для указания неограниченное число элементов данного типа сразу перед многоточием.<br /><br /> В коде многоточия обозначают код опущен для ясности.|  
|ESC, ВВЕДИТЕ|Имена ключей и сочетания клавиш на клавиатуре отображаются только прописными буквами.|  
|ALT + F1|Если между именами ключей отображаются плюс (+), необходимо удерживать нажатой клавишу один при нажатии второй. Например ALT + F1 означает удерживать нажатой клавишу ALT при нажатии клавиши F1.|  
  
## <a name="code-conventions"></a>Соглашения о написании кода  
  
|Пример|Описание|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Примеры кода, отображаются в моноширинный шрифт и форматируются как показано в следующем примере.|  
|Предыдущая инструкция устанавливает значение `sampleString` для «Hello, world!»|Элементы кода в пояснительного текста отображаются в моноширинный шрифт, как показано в следующем примере.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Комментарии к коду введенный символ апострофа (') или ключевое слово REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Пробел перед знаком подчеркивания (_) в конце строки указывает, что инструкция продолжается на следующей строке.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)  
 [Ключевые слова](../../visual-basic/language-reference/keywords/index.md)  
 [Члены библиотеки времени выполнения Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)  
 [Соглашения об именах Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [Комментарии в коде](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
