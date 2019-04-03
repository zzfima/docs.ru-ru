---
title: Определяемый пользователем тип (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5fe12d18c7f403c1a50ed548a260ba39e83280eb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814202"
---
# <a name="user-defined-data-type"></a>Тип данных, определенный пользователем
Содержит данные в формате, определяемом. `Structure` Инструкция определяет формат.  
  
 Предыдущие версии Visual Basic поддерживают определяемый пользователем тип (UDT). Текущая версия расширяет в определяемом пользователем ТИПЕ *структуры*. Структура — это объединение одного или нескольких *члены* различных типов данных. Visual Basic обрабатывает структуру как единое целое, несмотря на то, что можно получить также доступ к членам по отдельности.  
  
## <a name="remarks"></a>Примечания  
 Определение и использование типом структуры данных, при необходимости для объединения различных типов данных в единое целое, или если ни один из простых типов данных целей.  
  
 Значение по умолчанию типа структуры данных состоит из сочетания значений по умолчанию для всех его членов.  
  
## <a name="declaration-format"></a>Формат объявления  
 Объявление структуры начинается с [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) и заканчивается `End Structure` инструкции. `Structure` Оператор содержит имя структуры, которая также является идентификатором типа данных, определение структуры. Другие части кода можно использовать этот идентификатор для объявления переменных, параметров и функции возвращают значения того типа данных этой структуры.  
  
 Объявления между `Structure` и `End Structure` операторы определяют члены структуры.  
  
## <a name="member-access-levels"></a>Уровни доступа к членам  
 Необходимо объявить каждый член с помощью [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) или оператор, который определяет уровень доступа, такие как [открытый](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), или [Private](../../../visual-basic/language-reference/modifiers/private.md). Если вы используете `Dim` инструкции, по умолчанию уровня доступа к общедоступным.  
  
## <a name="programming-tips"></a>Советы по программированию  
  
-   **Потребление памяти.** Как и в случае всех составных типов данных, нельзя вычислить безопасно общее потребление памяти структуры путем сложения распределения Номинальное дисковое его членов. Кроме того нельзя рассчитывать на безопасно порядок элементов в памяти: так же, как порядок их объявления. Если вам нужно управлять макетом структуры хранилища, вы можете применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут `Structure` инструкции.  
  
-   **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например автоматизация или COM-объектов, имейте в виду, что определяемые пользователем типы в других средах не совместимы с Visual Basic типами структуры.  
  
-   **Расширяющие.** Нет автоматического преобразования в или из любого типа структуры данных. Операторы преобразования можно определить для структуры с помощью [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), вы можете объявить каждый оператор преобразования быть `Widening` или `Narrowing`.  
  
-   **Символы типа.** Типы данных структуры не имеют знак типа литерала или знак типа идентификатора.  
  
-   **Тип Framework.** Отсутствует соответствующий тип в .NET Framework. Все структуры наследуют от класса .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, но нет отдельных структура соответствует <xref:System.ValueType?displayProperty=nameWithType>.  
  
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

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
