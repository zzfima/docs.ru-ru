---
title: Вариативность в делегатах
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 11146bc4a60f55fc0373f0b5dfa5d44dcf748a5b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349004"
---
# <a name="variance-in-delegates-visual-basic"></a>Вариативность в делегатах (Visual Basic)

В .NET Framework 3,5 введена поддержка вариативности для сопоставления сигнатур методов с типами делегатов C# во всех делегатах в и Visual Basic. Это означает, что делегатам можно назначать не только методы, которые обладают соответствующими сигнатурами, но и методы, которые возвращают более производные типы (ковариация), или принимают параметры, которые имеют менее производные типы (контравариативность), чем указано в типе делегата. Это касается не только универсальных методов-делегатов, но и методов-делегатов, не являющихся универсальными.

Например, рассмотрим следующий код, который содержит два класса и два делегата: универсальный и неуниверсальный.

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

При создании делегатов типов `SampleDelegate` или `SampleDelegate(Of A, R)` им можно назначить любой из следующих методов.

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

В следующем примере кода показано неявное преобразование между сигнатурой метода и типом делегата.

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

Дополнительные примеры см. [в разделе Использование вариативности в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) и [Использование вариативности для универсальных делегатов Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

## <a name="variance-in-generic-type-parameters"></a>Вариативность в параметрах универсального типа

В .NET Framework 4 и более поздних версиях можно включить неявное преобразование между делегатами, чтобы универсальные делегаты с разными типами, заданными параметрами универсального типа, могли быть назначены друг другу, если типы наследуются друг от друга, как требуется для Вариация.

Чтобы включить неявное преобразование, необходимо явно объявить универсальные параметры в делегате как ковариантные или контравариантные с помощью ключевого слова `in` или `out`.

В следующем примере кода показано, как создать делегат, который имеет ковариантный параметр универсального типа.

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

Если поддержка вариативности используется только для сопоставления сигнатур методов с типами делегатов, а ключевые слова `in` и `out` не используются, можно создать экземпляры делегатов с одинаковыми лямбда-выражениями или методами, но нельзя назначить один делегат другому.

В следующем примере кода `SampleGenericDelegate(Of String)` не может быть явно преобразован в `SampleGenericDelegate(Of Object)`, хотя `String` наследует `Object`. Эту проблему можно устранить, пометив универсальный параметр `T` ключевым словом `out`.

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Универсальные методы-делегаты с вариативными параметрами типа в .NET Framework

В платформе .NET Framework 4 появилась поддержка вариативности для параметров универсального типа в нескольких существующих методах-делегатах.

- Делегаты `Action` из пространства имен <xref:System>, например <xref:System.Action%601> и <xref:System.Action%602>

- Делегаты `Func` из пространства имен <xref:System>, например <xref:System.Func%601> и <xref:System.Func%602>

- Делегат <xref:System.Predicate%601>

- Делегат <xref:System.Comparison%601>

- Делегат <xref:System.Converter%602>

Дополнительные сведения и примеры см. [в разделе Использование вариативности универсальных делегатов Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Объявление вариативных параметров типа в универсальных методах-делегатах

Если универсальный метод-делегат содержит ковариантные или контравариантные параметры универсального типа, он называется *вариативным универсальным методом-делегатом*.

Для объявления ковариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `out`. Ковариантный тип можно использовать только в качестве типа значения, возвращаемого методом, и нельзя использовать в качестве типа аргументов метода. В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

Для объявления контравариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `in`. Контравариантный тип можно использовать только в качестве типа аргументов метода, и нельзя использовать в качестве типа значения, возвращаемого методом. В следующем примере кода показано, как объявить контравариантный универсальный метод-делегат.

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> `ByRef` параметры в Visual Basic не могут быть помечены как Variant.

В одном делегате можно реализовать поддержку вариативности и ковариации, но для разных параметров типа. Эти действия показаны в следующем примере.

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Создание экземпляра и вызов вариативных универсальных методов-делегатов

Создание экземпляра и вызов вариативных делегатов возможен только при создании экземпляра и вызове инвариантных делегатов. В следующем примере создается экземпляр делегата с помощью лямбда-выражения.

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a>Объединение вариативных универсальных методов-делегатов

Не следует объединять вариантные делегаты. Метод <xref:System.Delegate.Combine%2A> не поддерживает преобразование вариантных делегатов и ожидает делегаты того же самого типа. Это может привести к исключению времени выполнения при объединении делегатов с помощью метода <xref:System.Delegate.Combine%2A> (в C# и Visual Basic) или с помощью оператора `+` (в C#), как показано в следующем примере кода.

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Вариативность в параметрах универсального типа для значения и ссылочных типов

Вариативность для параметров универсального типа поддерживается только для ссылочных типов. Например, `DVariant(Of Int)`нельзя неявно преобразовать в `DVariant(Of Object)` или `DVariant(Of Long)`, так как тип Integer является типом значения.

В следующем примере показано, что вариативность в параметрах универсального типа не поддерживается для типов значения.

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Неявное преобразование делегата в Visual Basic

Неявное преобразование делегатов обеспечивает большую гибкость при сопоставлении сигнатур методов с типами делегатов. Например, он позволяет опускать спецификации параметров и опускать возвращаемые значения функции при назначении метода делегату. Дополнительные сведения см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).

## <a name="see-also"></a>См. также

- [Универсальные шаблоны](../../../../standard/generics/index.md)
- [Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
