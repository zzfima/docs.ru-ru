---
title: "Тип данных, определенный пользователем"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e1876d61a2ce89b04c6e5061b868f0be365639f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-data-type"></a>Тип данных, определенный пользователем
Содержит данные в формате, определяемом. `Structure` Инструкция определяет формат.  
  
 Предыдущие версии Visual Basic поддерживают определяемый пользователем тип (UDT). Текущая версия расширяет в определяемом пользователем ТИПЕ *структуры*. Структура — это объединение одного или нескольких *члены* различных типов данных. Visual Basic обрабатывает структуру как единый блок, хотя также можно использовать его члены по отдельности.  
  
## <a name="remarks"></a>Примечания  
 Определять и использовать тип структуры данных, когда необходимо объединить различные типы данных в одну единицу или когда ни одна из простейших типов данных соответствует конкретным требованиям.  
  
 Значение по умолчанию типа структуры данных состоит из комбинации значений по умолчанию для каждого из его членов.  
  
## <a name="declaration-format"></a>Формат объявления  
 Объявление структуры начинается с [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) и заканчивается `End``Structure` инструкции. `Structure` Оператор содержит имя структуры, которая является также идентификатором типа данных, определение структуры. Другие части кода можно использовать этот идентификатор для объявления переменных, параметров и функции возвращают значения типа данных этой структуры.  
  
 Объявления между `Structure` и `End``Structure` инструкции определения членов структуры.  
  
## <a name="member-access-levels"></a>Уровни доступа к членам  
 Необходимо объявить каждый член с помощью [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) или инструкцию, которая определяет уровень доступа, например [открытый](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), или [частного](../../../visual-basic/language-reference/modifiers/private.md). Если вы используете `Dim` оператора, по умолчанию уровня доступа к открытым.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Потребление памяти.** Как и все составные типы данных, нельзя вычислить безопасно общее потребление памяти структуры путем сложения выделения Номинальное дисковое его члены. Более того нельзя безошибочно полагать, что порядок расположения элементов в памяти является таким же, как и порядок их объявления. Если вам необходимо управлять структуры хранилища структуры, можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут `Structure` инструкции.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например автоматизации или COM-объекты, необходимо помнить, что определяемые пользователем типы в других средах не совместимы с Visual Basic типами структуры.  
  
-   **Расширяющие.** Нет автоматического преобразования в или из любой тип данных структуры. Можно определить операторы преобразования структуры с помощью [оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md), и можно объявить каждый оператор преобразования быть `Widening` или `Narrowing`.  
  
-   **Символы типов.** Типы данных структуры не имеют буквенного символа или знак типа идентификатора.  
  
-   **Тип Framework.** Нет соответствующих типов в .NET Framework. Все структуры наследуют от класса .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, но не отдельные структура соответствует <xref:System.ValueType?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется структура объявления структуры.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
