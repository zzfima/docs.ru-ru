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
ms.openlocfilehash: cb7e9f2a577e95e09fde885df1a78aea4e7fa466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651922"
---
# <a name="visual-basic-naming-conventions"></a>Соглашения об именах Visual Basic
При задании имени элемента в приложении Visual Basic, первый символ с тем же именем необходимо буквы алфавита или знака подчеркивания. Обратите внимание, что имена, начинающиеся с символа подчеркивания, не совместимы с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Следующие советы для именования.  
  
-   Начинать каждое отдельное слово в имени с прописной буквы, например `FindLastRecord` и `RedrawMyForm`.  
  
-   Начинать имена функций и методов с глагола, например `InitNameArray` или `CloseDialog`.  
  
-   Начинать класс, структура, модуль и имена свойств с существительного, например `EmployeeName` или `CarAccessory`.  
  
-   Первым в имени интерфейса с префиксом «I», следуют существительного или субстантивное словосочетание, таких как `IComponent`, или прилагательное, описывающее поведение интерфейса, например `IPersistable`. Не используйте символ подчеркивания и аббревиатуры, поскольку аббревиатуры могут ввести в заблуждение.  
  
-   Имена обработчиков событий начинать с имени существительного, описывающего тип события, за которым следует "`EventHandler`«как в следующем примере, суффикс»`MouseEventHandler`».  
  
-   К именам аргументов классов событий следует добавлять «`EventArgs`» суффикс.  
  
-   Если событие имеет смысл «до» или «после», используйте суффикс в настоящее или прошедшее время, как в «`ControlAdd`«или»`ControlAdded`».  
  
-   Для длинных или часто используемых терминов используйте аббревиатуры разумной длины, например, «HTML» вместо «Язык HTML». В общем случае имена переменных длиной более 32 символов трудно читать на мониторе с низким разрешением. Кроме того убедитесь, что ваш сокращения согласованы во всем приложении. Переключение случайным образом в проекте между «HTML» и «Язык HTML» может привести к путанице.  
  
-   Избегайте использования во внутренней области имен, которые совпадают с именами во внешней области. Ошибки могут привести случае доступа к неправильной переменной. Если конфликт возникает между переменной и ключевого слова с тем же именем, необходимо указать ключевое слово перед ее именем соответствующей библиотеки типов. Например, если есть переменная `Date`, можно использовать встроенную функцию `Date` функции только путем вызова <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова как имена элементов в коде](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)
