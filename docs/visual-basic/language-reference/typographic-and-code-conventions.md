---
title: Условные обозначения и соглашения о коде (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: 3255dff8268cd5500a1244716f37bf30f5b43cfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698607"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Условные обозначения и соглашения о коде (Visual Basic)
Документация по Visual Basic использует следующие условные обозначения и соглашения о написании кода.  
  
## <a name="typographic-conventions"></a>Соглашения о печати  
  
|Пример|Описание|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Зарезервированные слова языка и среды выполнения элементов имеют начальные прописные буквы и форматируются, как показано в следующем примере.|  
|**SmallProject**, **ButtonCollection**|Слова и фразы, будет предложено ввести форматируются так, как показано в следующем примере.|  
|[Оператор Module](../../visual-basic/language-reference/statements/module-statement.md)|Ссылки, которые можно щелкнуть для перехода на другую страницу справки, форматируются как показано в следующем примере.|  
|*Объект*, *variableName*, `argumentList`|Заполнители для информации, указываемое в форматируются, как показано в следующем примере.|  
|[Shadows], [ *expressionList* ]|В синтаксисе необязательные элементы заключаются в квадратные скобки.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|Если необходимо сделать выбор между двумя или несколькими элементами, элементы в синтаксисе, заключенный в фигурные скобки и разделяются вертикальной чертой.<br /><br /> Необходимо выбрать один и только один из элементов.|  
|[ `Protected` &#124; `Friend` ]|Если у вас есть возможность выбора между двумя или несколькими элементами, элементы в синтаксисе, заключенная в квадратные скобки и разделяются вертикальной чертой.<br /><br /> Можно выбрать любое сочетание элементов, или ни один элемент.|  
|[{ `ByVal` &#124; `ByRef` }]|В синтаксисе когда можно выбрать не более одного элемента, но можно также опустить элементы полностью, элементы заключаются в квадратные скобки заключены в фигурные скобки и разделяются вертикальной чертой.|  
|*имя пользователя*1, *memberName*2, *memberName*3|Несколько экземпляров в одной позиции отличаются подстрочные знаки, как показано в примере.|  
|*Имя_члена1*<br /><br /> ...<br /><br /> *memberNameN*|В синтаксисе многоточие (...) используется для указания неограниченное число элементов типа сразу перед многоточием.<br /><br /> В коде многоточие обозначают опустить ради ясности кода.|  
|ESC, ВВЕДИТЕ|Имена ключей и сочетания клавиш на клавиатуре отображаются прописными буквами.|  
|ALT+F1|Когда плюс (+) отображается между именами ключей, необходимо удерживайте один ключ, при нажатии второй. Например ALT + F1 означает удерживать нажатой клавишу ALT при нажатии клавиши F1.|  
  
## <a name="code-conventions"></a>Соглашения о коде  
  
|Пример|Описание|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Примеры кода отображаются в моноширинный шрифт и форматируются, как показано в следующем примере.|  
|Предыдущая инструкция устанавливает значение `sampleString` для «Hello, world!»|Элементы кода в пояснительный текст отображаются в моноширинный шрифт, как показано в следующем примере.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Комментарии к коду, представленные апостроф (') или ключевое слово REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Пробел перед знаком подчеркивания (_) в конце строки указывает, что инструкция продолжается на следующей строке.|  
  
## <a name="see-also"></a>См. также

- [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)
- [Ключевые слова](../../visual-basic/language-reference/keywords/index.md)
- [Члены библиотеки времени выполнения Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)
- [Соглашения об именах Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Комментарии в коде](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
