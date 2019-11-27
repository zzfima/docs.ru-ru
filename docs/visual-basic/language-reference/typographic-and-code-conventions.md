---
title: Условные обозначения и соглашения о коде
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
ms.openlocfilehash: 4906c5ebadb7ce77f2d0e53b2fc5dbab69c5b41f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352704"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Условные обозначения и соглашения о коде (Visual Basic)

В Visual Basic документации используются следующие типографские и программные соглашения.  
  
## <a name="typographic-conventions"></a>Типографские соглашения  
  
|Пример|Описание|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Ключевые слова и члены среды выполнения, относящиеся к конкретному языку, имеют начальные прописные буквы и форматируются, как показано в этом примере.|  
|**Смаллпрожект**, **буттонколлектион**|Слова и фразы, которые вы указываете ввести, форматируются, как показано в этом примере.|  
|[Оператор Module](../../visual-basic/language-reference/statements/module-statement.md)|Ссылки, которые можно щелкнуть для перехода на другую страницу справки, форматируются, как показано в этом примере.|  
|*Object*, *variablename*, `argumentList`|Заполнители для предоставленной информации форматируются, как показано в этом примере.|  
|[Shadows], [ *експрессионлист* ]|В синтаксисе необязательные элементы заключаются в квадратные скобки.|  
|{`Public` &#124; `Friend` &#124; `Private`}|В синтаксисе, когда необходимо выбрать между двумя или более элементами, элементы заключаются в фигурные скобки и разделяются вертикальными линиями.<br /><br /> Необходимо выбрать один и только один из элементов.|  
|[`Protected` &#124; `Friend`]|В синтаксисе, если имеется возможность выбора между двумя или более элементами, элементы заключаются в квадратные скобки и разделяются вертикальными линиями.<br /><br /> Можно выбрать любое сочетание элементов или без элемента.|  
|[{`ByVal` &#124; `ByRef`}]|В синтаксисе, если можно выбрать не более одного элемента, но можно полностью опустить элементы, элементы будут заключены в квадратные скобки, заключенные в фигурные скобки и разделенные вертикальными чертами.|  
|*MemberName*1, *MemberName*2, *MemberName*3|Несколько экземпляров одного и того же заполнителя различаются по индексам, как показано в примере.|  
|*memberName1*<br /><br /> ...<br /><br /> *мембернамен*|В синтаксисе многоточие (...) используется для обозначения неопределенного числа элементов типа непосредственно перед многоточием.<br /><br /> В коде многоточие обозначает код, опущенный для простоты.|  
|ESC, ВВЕДИТЕ|Имена ключей и последовательности клавиш на клавиатуре отображаются во всех прописных буквах.|  
|ALT+F1|Если между именами ключей появляются знаки плюса (+), необходимо удерживать один ключ, а затем нажать другой. Например, ALT + F1 означает, что при нажатии клавиши F1 удерживайте нажатой клавишу ALT.|  
  
## <a name="code-conventions"></a>Соглашения о коде  
  
|Пример|Описание|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Примеры кода отображаются в шрифте фиксированной высоты и форматируются, как показано в этом примере.|  
|Предыдущая инструкция задает для `sampleString` значение "Hello, World!".|Элементы кода в пояснительном тексте отображаются в виде шрифта фиксированной высоты, как показано в этом примере.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Комментарии к коду вводятся с помощью апострофа (') или ключевого слова REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Пробел, за которым следует символ подчеркивания (_) в конце строки, означает, что инструкция продолжится в следующей строке.|  
  
## <a name="see-also"></a>См. также

- [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)
- [Ключевые слова](../../visual-basic/language-reference/keywords/index.md)
- [Члены библиотеки времени выполнения Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)
- [Соглашения об именовании Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Комментарии в коде](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
