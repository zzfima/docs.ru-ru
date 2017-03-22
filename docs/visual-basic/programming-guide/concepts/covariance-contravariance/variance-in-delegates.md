---
title: "Вариативность в делегатах (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a>Вариативность в делегатах (Visual Basic)
.NET framework 3.5 представила поддержка вариативности при сопоставлении сигнатур методов с типами делегатов в все делегаты в C# и Visual Basic. Это означает, что можно назначить делегирует не только методы, которые обладают соответствующими сигнатурами, но методы, которые возвращают более производные типы (ковариация) или принимают параметры, которые имеют менее производные типы (контравариация), чем указано в типе делегата. Сюда входят универсальных и неуниверсальных делегатах.  
  
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
  
 При создании делегатов `SampleDelegate` или `SampleDelegate(Of A, R)` типов, можно назначить один из следующих методов этих делегатов.  
  
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
  
 В следующем примере кода показано неявное преобразование между сигнатуру метода и тип делегата.  
  
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
  
 Дополнительные примеры см. в разделе [с помощью Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) и [с помощью дисперсию Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
## <a name="variance-in-generic-type-parameters"></a>Вариативность в параметрах универсального типа  
 В .NET Framework 4 и более поздних версий неявное преобразование между делегатами, можно включить, чтобы универсальные делегаты, которые имеют разные типы, указанные параметрами универсального типа можно назначить друг к другу, если типы наследуются друг от друга, как требует вариативность.  
  
 Чтобы включить неявное преобразование, необходимо явно объявить универсальные параметры в делегате как ковариантные или контравариантные с помощью `in` или `out` ключевое слово.  
  
 В следующем примере кода показано, как можно создать делегат, который имеет ковариантный параметр универсального типа.  
  
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
  
 Если только поддержка вариативности используется для сопоставления сигнатур методов с типами делегатов, а не используйте `in` и `out` ключевые слова, вы обнаружите, что можно создать экземпляры делегатов с одинаковыми лямбда-выражениями или методами, но нельзя назначить один делегат другому.  
  
 В следующем примере кода `SampleGenericDelegate(Of String)` не может быть явно преобразованы `SampleGenericDelegate(Of Object)`, хотя `String` наследует `Object`. Эту проблему можно устранить, пометив универсальный параметр `T` с `out` ключевое слово.  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Универсальные делегаты, которые имеют вариант параметрами типа в .NET Framework  
 Платформа .NET framework 4 появилась поддержка вариативности для параметров универсального типа в нескольких существующих универсальных методов-делегатов:  
  
-   `Action`делегирует с <xref:System>пространства имен, например, <xref:System.Action%601>и <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System>  
  
-   `Func`делегирует с <xref:System>пространства имен, например, <xref:System.Func%601>и <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System>  
  
-   <xref:System.Predicate%601>Делегат</xref:System.Predicate%601>  
  
-   <xref:System.Comparison%601>Делегат</xref:System.Comparison%601>  
  
-   <xref:System.Converter%602>Делегат</xref:System.Converter%602>  
  
 Дополнительные сведения и примеры см. в разделе [с помощью дисперсию Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Объявление параметров типа Variant в универсальных методах-делегатах  
 Если универсальный метод-делегат содержит ковариантные или контравариантные параметры универсального типа, он может называться *вариантных универсальных делегатов*.  
  
 Параметр универсального типа можно объявить ковариантный универсальный делегат с помощью `out` ключевое слово. Параметры ковариантного типа может использоваться только в качестве типа возвращаемого значения метода, а не как тип аргументов метода. В следующем примере кода показано, как объявить ковариантный универсальный делегат.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 Контравариантного параметра универсального типа в универсальный делегат можно объявить с помощью `in` ключевое слово. Контравариантный тип можно использовать только в качестве типа аргументов метода, а не как тип возвращаемого значения метода. В следующем примере кода показано, как объявить контравариантный универсальный делегат.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  `ByRef`в Visual Basic не может быть помечен как данные variant.  
  
 Также можно реализовать поддержку вариативности и ковариации в тот же делегат, но для разных параметров типа. Эти действия показаны в следующем примере.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Создание экземпляра и вызов вариативных универсальных методов-делегатов  
 Можно создать и вызов вариативных делегатов как экземпляра и вызове инвариантных делегатов. В следующем примере создается экземпляр делегата, лямбда-выражение.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
### <a name="combining-variant-generic-delegates"></a>Объединение вариативных универсальных методов-делегатов  
 Не следует объединять вариантные делегаты. <xref:System.Delegate.Combine%2A>Метод не поддерживает преобразование вариантных делегатов и ожидает делегаты точно того же типа.</xref:System.Delegate.Combine%2A> Это может привести к исключение времени выполнения при объединении делегатов с помощью <xref:System.Delegate.Combine%2A>метод (в C# и Visual Basic) или с помощью `+` оператора (в C#), как показано в следующем примере кода.</xref:System.Delegate.Combine%2A>  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Вариативность в параметрах универсального типа для значений и ссылочные типы  
 Вариативность для параметров универсального типа поддерживается только для ссылочных типов. Например `DVariant(Of Int)`не может быть неявно преобразован к `DVariant(Of Object)` или `DVariant(Of Long)`, так как целое число — это тип значения.  
  
 В следующем примере показано, что Вариативность в универсальных типов параметров не поддерживается для типов значений.  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Неявное преобразование делегата в Visual Basic  
 Неявное преобразование делегата обеспечивает большую гибкость при сопоставлении сигнатур методов с типами делегатов. Например он позволяет опустить спецификации параметров и опустить возвращаемые значения функции при назначении метода делегату. Дополнительные сведения см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="see-also"></a>См. также  
 [Универсальные шаблоны](https://msdn.microsoft.com/library/ms172192)   
 [Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
