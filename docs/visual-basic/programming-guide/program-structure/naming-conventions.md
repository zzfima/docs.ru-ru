---
title: Соглашения об именах
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
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347311"
---
# <a name="visual-basic-naming-conventions"></a>Соглашения об именах Visual Basic
При именовании элемента в Visual Basic приложении первым символом этого имени должна быть буква или символ подчеркивания. Однако обратите внимание, что имена, начинающиеся со знака подчеркивания, не соответствуют [языку, независимому от языка и языковых компонентов](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Следующие рекомендации применимы к именованию.  
  
- Начинайте каждое отдельное слово в имени с заглавной буквой, как в `FindLastRecord` и `RedrawMyForm`.  
  
- Начинайте имена функций и методов с помощью глагола, как в `InitNameArray` или `CloseDialog`.  
  
- Имена классов, структур, модулей и свойств следует начинать с существительных, как в `EmployeeName` или `CarAccessory`.  
  
- Имена интерфейсов начинаются с префикса "I", за которым следует существительное или существительное, например `IComponent`, или с прилагательным, описывающим поведение интерфейса, например `IPersistable`. Не используйте символ подчеркивания и используйте сокращения экономно, поскольку аббревиатуры могут вызвать путаницу.  
  
- Передайте имена обработчиков событий с существительным, описывающим тип события, за которым следует суффикс "`EventHandler`", как в "`MouseEventHandler`".  
  
- В именах классов аргументов событий включите суффикс "`EventArgs`".  
  
- Если событие имеет концепцию "до" или "после", используйте суффикс в настоящем или прошедшем прошлом, например "`ControlAdd`" или "`ControlAdded`".  
  
- Для длинных или часто используемых терминов используйте аббревиатуры, чтобы обеспечить приемлемую длину имен, например "HTML", а не "HTML". В общем случае имена переменных, длина которых превышает 32 символов, трудно прочитать на мониторе, для которого задано низкое разрешение. Кроме того, убедитесь, что аббревиатуры согласованы во всем приложении. Случайное переключение в проект между "HTML" и "HTML" может привести к путанице.  
  
- Старайтесь не использовать имена во внутренней области, имена которых совпадают с именами во внешней области. Если доступ к неправильной переменной будет осуществлен, могут возникнуть ошибки. Если возникает конфликт между переменной и ключевым словом с тем же именем, необходимо сначала обозначить ключевое слово, указав его перед соответствующей библиотекой типов. Например, если имеется переменная с именем `Date`, можно использовать встроенную функцию `Date` только путем вызова <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- [Ключевые слова как имена элементов в коде](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)
