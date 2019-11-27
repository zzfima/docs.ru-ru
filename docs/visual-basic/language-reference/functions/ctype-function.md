---
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 18b2d5a28cd6ef885ba8d237da6764dbbd108b59
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348099"
---
# <a name="ctype-function-visual-basic"></a>Функция CType (Visual Basic)

Возвращает результат явного преобразования выражения в указанный тип данных, объект, структуру, класс или интерфейс.

## <a name="syntax"></a>Синтаксис

```vb
CType(expression, typename)
```

## <a name="parts"></a>Части

`expression` любое допустимое выражение. Если значение `expression` находится вне диапазона, разрешенного `typename`, Visual Basic создает исключение.

`typename` любое выражение, которое является допустимым в предложении `As` в операторе `Dim`, то есть имя любого типа данных, объекта, структуры, класса или интерфейса.

## <a name="remarks"></a>Примечания

> [!TIP]
> Для преобразования типов также можно использовать следующие функции.
>
> - Функции преобразования типов, такие как `CByte`, `CDbl`и `CInt`, которые выполняют преобразование в конкретный тип данных. Дополнительные сведения см. в разделе [функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).
> - Оператор [DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Для этих операторов требуется, чтобы один тип наследовал или реализовывал другой тип. Они могут обеспечить более высокую производительность, чем `CType` при преобразовании в тип данных `Object` и из него.

`CType` компилируется встроенным образом. Это означает, что код преобразования является частью кода, который вычисляет выражение. В некоторых случаях код выполняется быстрее, так как для выполнения преобразования не вызываются никакие процедуры.

Если преобразование из `expression` в `typename` не определено (например, из `Integer` в `Date`), Visual Basic выводит сообщение об ошибке времени компиляции.

Если во время выполнения происходит сбой преобразования, выдается соответствующее исключение. Если сужение преобразования завершается неудачно, то наиболее распространенным результатом является <xref:System.OverflowException>. Если преобразование не определено, создается <xref:System.InvalidCastException>. Например, это может произойти, если `expression` имеет тип `Object` и тип времени выполнения не преобразуется в `typename`.

Если тип данных `expression` или `typename` является определенным классом или структурой, можно определить `CType` в этом классе или структуре как оператор преобразования. Это делает `CType` действовать в качестве *перегруженного оператора*. В этом случае можно управлять поведением преобразований в класс или структуру, включая исключения, которые могут быть созданы.

## <a name="overloading"></a>Перегрузка

Оператор `CType` можно также перегрузить в классе или структуре, определенной вне кода. Если код преобразует в или из такого класса или структуры, убедитесь, что вы понимаете поведение его оператора `CType`. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Преобразование динамических объектов

Преобразования типов динамических объектов выполняются с помощью определяемых пользователем динамических преобразований, использующих методы <xref:System.Dynamic.DynamicObject.TryConvert%2A> или <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>. При работе с динамическими объектами используйте метод <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> для преобразования динамического объекта.

## <a name="example"></a>Пример

В следующем примере функция `CType` используется для преобразования выражения в тип данных `Single`.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Дополнительные примеры см. в разделе [явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>См. также

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Функции преобразования](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Преобразование типов в .NET Framework](../../../standard/base-types/type-conversion.md)
