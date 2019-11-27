---
title: Тип данных, определенный пользователем
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
ms.openlocfilehash: 99eeb4b619f6bb23d00f8e449de953d41843f714
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343868"
---
# <a name="user-defined-data-type"></a>Тип данных, определенный пользователем

Хранит данные в определенном формате. Оператор `Structure` определяет формат.

Предыдущие версии Visual Basic поддерживают определяемый пользователем тип (UDT). Текущая версия расширяет определяемый пользователем тип на *структуру*. Структура — это объединение одного или нескольких *элементов* различных типов данных. Visual Basic обрабатывает структуру как единое целое, хотя вы также можете обращаться к ее членам по отдельности.

## <a name="remarks"></a>Примечания

Определяйте и используйте тип данных Structure, если необходимо объединить различные типы данных в один блок или если ни один из простейших типов данных не подходит для ваших нужд.

Значение по умолчанию для типа данных Structure состоит из сочетания значений по умолчанию для каждого из его элементов.

## <a name="declaration-format"></a>Формат объявления

Объявление структуры начинается с [оператора Structure](../../../visual-basic/language-reference/statements/structure-statement.md) и заканчивается оператором `End Structure`. Инструкция `Structure` предоставляет имя структуры, которая также является идентификатором типа данных, определяемого структурой. Другие части кода могут использовать этот идентификатор для объявления переменных, параметров и возвращаемых значений функций в качестве типа данных этой структуры.

Объявления между операторами `Structure` и `End Structure` определяют элементы структуры.

## <a name="member-access-levels"></a>Уровни доступа к членам

Каждый член необходимо объявить с помощью [оператора Dim](../../../visual-basic/language-reference/statements/dim-statement.md) или оператора, определяющего уровень доступа, например [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md)или [Private](../../../visual-basic/language-reference/modifiers/private.md). При использовании оператора `Dim` уровень доступа по умолчанию равен public.

## <a name="programming-tips"></a>Советы по программированию

- **Потребление памяти.** Как и для всех составных типов данных, вы не можете безопасно вычислить общее потребление памяти для структуры, добавив в них номинальные объемы выделяемого пространства для его членов. Кроме того, нельзя безопасно предположить, что порядок хранения в памяти совпадает с порядком объявления. Если необходимо управлять структурой хранилища структуры, можно применить атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> к инструкции `Structure`.

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что определяемые пользователем типы в других средах несовместимы с типами структуры Visual Basic.

- **Расширяющие.** Автоматическое преобразование в любой тип данных структуры или из него отсутствует. Операторы преобразования в структуре можно определить с помощью оператора [оператора](../../../visual-basic/language-reference/statements/operator-statement.md), а каждый оператор преобразования можно объявить `Widening` или `Narrowing`.

- **Символы типа.** Типы данных структуры не имеют символа литерального типа или символа типа идентификатора.

- **Тип платформы.** В .NET Framework нет соответствующего типа. Все структуры наследуют от класса .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, но никакие отдельные структуры не соответствуют <xref:System.ValueType?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующей парадигме показана структура объявления структуры.

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a>См. также:

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Расширение](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
