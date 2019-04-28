---
title: Функция CType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: dbf01263723a9e2890dab57d5ffc3d467ed250fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801683"
---
# <a name="ctype-function-visual-basic"></a>Функция CType (Visual Basic)

Возвращает результат явного преобразования выражения для указанного типа данных, объекта, структуры, класса или интерфейса.

## <a name="syntax"></a>Синтаксис

```
CType(expression, typename)
```

## <a name="parts"></a>Части

`expression` Любое допустимое выражение. Если значение `expression` находится за пределами диапазона, разрешенного `typename`, Visual Basic создает исключение.

`typename` Любое выражение, которое является допустимым в пределах `As` предложение в `Dim` инструкции, то есть имя типа данных, объекта, структуры, класса или интерфейса.

## <a name="remarks"></a>Примечания

> [!TIP]
> Для выполнения преобразования типов также можно использовать следующие функции:
>
> - Функции преобразования типа, таких как `CByte`, `CDbl`, и `CInt` , которые выполняют преобразование к определенному типу данных. Дополнительные сведения см. в разделе [функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).
> - [Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Эти операторы требуют наследовать от одного типа или реализовывал другой тип. Они могут предоставить несколько более высокую производительность, чем `CType` при преобразовании значений с `Object` тип данных.

`CType` — компилируется путем подстановки, это означает, что код преобразования является частью кода, вычисляет выражение. В некоторых случаях код выполняется быстрее, так как ни одной процедуры вызываются для выполнения преобразования.

Если не определено преобразование из `expression` для `typename` (например, из `Integer` для `Date`), Visual Basic отображает сообщение об ошибке времени компиляции.

При сбое преобразования во время выполнения, возникает соответствующее исключение. При сбое сужающего преобразования <xref:System.OverflowException> является наиболее распространенным результатом. Если преобразование не определено, <xref:System.InvalidCastException> исключение. Например, это может произойти, если `expression` имеет тип `Object` и его тип времени выполнения не имеет преобразования в `typename`.

Если тип данных `expression` или `typename` — это класс или структуру, вы определили, можно определить `CType` для этого класса или структуры в качестве оператора преобразования. Это делает `CType` выступать в качестве *перегруженный оператор*. После этого можно управлять поведением преобразования в и из класса или структуры, включая исключения, которые могут создаваться.

## <a name="overloading"></a>Перегрузка

`CType` Оператор также может быть перегружен для класса или структуры, определяемой вне данного кода. Если код осуществляет преобразование в или из такого класса или структуры, убедитесь, что вы понимаете поведение его `CType` оператор. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Преобразование динамических объектов

Тип преобразования динамических объектов выполняются через определяемые пользователем преобразованиями, использующего <xref:System.Dynamic.DynamicObject.TryConvert%2A> или <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> методы. Если вы работаете с динамическими объектами, используйте <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> метод для преобразования динамический объект.

## <a name="example"></a>Пример

В следующем примере используется `CType` функцию для преобразования выражения `Single` тип данных.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Дополнительные примеры см. в разделе [явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>См. также

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Функции преобразования](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Преобразование типов в .NET Framework](../../../standard/base-types/type-conversion.md)
