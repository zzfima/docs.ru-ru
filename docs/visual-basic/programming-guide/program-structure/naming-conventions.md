---
title: Соглашения об именах Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: ebb9d21e32993f2eb035993d32dc3de7d97b49f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672140"
---
# <a name="visual-basic-naming-conventions"></a>Соглашения об именах Visual Basic
При вводе имени элемента в приложении Visual Basic, первый символ имени должны быть буквы или символа подчеркивания. Обратите внимание, что имена, начинающиеся с символа подчеркивания, не совместимы с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Следующие советы для именования.  
  
-   Начинать каждое отдельное слово в имени с заглавной буквы, например `FindLastRecord` и `RedrawMyForm`.  
  
-   Начинать имена функций и методов с глагола, например `InitNameArray` или `CloseDialog`.  
  
-   Начинать класса, структуры, модуля и имен свойств с существительного, например `EmployeeName` или `CarAccessory`.  
  
-   Начать интерфейс именами с префиксом «I», следуют существительного или субстантивное словосочетание, например `IComponent`, или прилагательное, описывающее поведение интерфейса, например `IPersistable`. Не используйте символ подчеркивания и аббревиатуры, так как сокращения могут привести к путанице.  
  
-   Имена обработчиков событий начинать с имени существительного, описывающего тип события, за которым следует "`EventHandler`«как в, суффикс»`MouseEventHandler`«.  
  
-   В именах классов аргументов событий, включают "`EventArgs`" суффикс.  
  
-   Если событие имеет смысл «до» или «после», используйте суффикс в настоящем или прошедшем времени, как в "`ControlAdd`«или»`ControlAdded`«.  
  
-   Для длинных или часто используемых терминов используйте аббревиатуры разумной длины, например, «HTML» вместо «Язык HTML». Как правило более 32 символов в именах переменных учитывается трудно читать на мониторе с разрешением с низким разрешением. Кроме того убедитесь, что ваш сокращения являются согласованными во всем приложении. Число случайных переключений в проекте между «HTML» и «Языка гипертекстовой разметки» может привести к путанице.  
  
-   Старайтесь не использовать имена во внутренней области, совпадающие с именами во внешней области. Ошибки могут привести к при обращении к неправильной переменной. Если возникает конфликт между переменной и ключевого слова с тем же именем, необходимо указать ключевое слово, перед которой стоят соответствующей библиотеки типов. Например, если у вас есть переменная с именем `Date`, можно использовать встроенный `Date` функции только путем вызова <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- [Ключевые слова как имена элементов в коде](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)
