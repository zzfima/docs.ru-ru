---
title: Ковариация и контрвариация
ms.date: 07/20/2015
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
ms.openlocfilehash: a75970d98890cb1fb363d4672bd90d376bccf89c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352144"
---
# <a name="covariance-and-contravariance-visual-basic"></a>Ковариация и контрвариантность (Visual Basic)

В Visual Basic ковариация и контрвариантность позволяют использовать неявное преобразование ссылок для типов массивов и делегатов, а также для аргументов универсального типа. Ковариация сохраняет совместимость присваивания, а при контрвариантности присваивание начинает работать противоположным образом.

Следующий код показывает разницу между совместимостью присваивания, ковариацией и контрвариантностью.

```vb
' Assignment compatibility.
Dim str As String = "test"
' An object of a more derived type is assigned to an object of a less derived type.
Dim obj As Object = str

' Covariance.
Dim strings As IEnumerable(Of String) = New List(Of String)()
' An object that is instantiated with a more derived type argument
' is assigned to an object instantiated with a less derived type argument.
' Assignment compatibility is preserved.
Dim objects As IEnumerable(Of Object) = strings

' Contravariance.
' Assume that there is the following method in the class:
' Shared Sub SetObject(ByVal o As Object)
' End Sub
Dim actObject As Action(Of Object) = AddressOf SetObject

' An object that is instantiated with a less derived type argument
' is assigned to an object instantiated with a more derived type argument.
' Assignment compatibility is reversed.
Dim actString As Action(Of String) = actObject
```

Ковариация для массивов позволяет неявно преобразовать массив более производного типа в массив менее производного типа. Но эта операция не является типобезопасной, как показано в следующем примере кода.

```vb
Dim array() As Object = New String(10) {}
' The following statement produces a run-time exception.
' array(0) = 10
```

Поддержка ковариации и контрвариантности для групп методов позволяет сопоставить сигнатуры методов с типами делегатов. За счет этого вы можете назначать делегатам не только методы с совпадающими сигнатурами, но и методы, которые возвращают более производные типы (ковариация) или принимают параметры с менее производными типами (контрвариантность), чем задает тип делегата. Дополнительные сведения см. в разделах [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).

В следующем примере кода демонстрируется поддержка ковариации и контрвариантности для групп методов.

```vb
Shared Function GetObject() As Object
    Return Nothing
End Function

Shared Sub SetObject(ByVal obj As Object)
End Sub

Shared Function GetString() As String
    Return ""
End Function

Shared Sub SetString(ByVal str As String)

End Sub

Shared Sub Test()
    ' Covariance. A delegate specifies a return type as object,
    ' but you can assign a method that returns a string.
    Dim del As Func(Of Object) = AddressOf GetString

    ' Contravariance. A delegate specifies a parameter type as string,
    ' but you can assign a method that takes an object.
    Dim del2 As Action(Of String) = AddressOf SetObject
End Sub
```

В .NET Framework 4 или более поздней версии Visual Basic поддерживает ковариации и контрвариация в универсальных интерфейсах и делегатах и позволяет неявное преобразование параметров универсального типа. Дополнительные сведения см. в разделах [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) и [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).

В следующем примере кода показано неявное преобразование ссылок для универсальных интерфейсов.

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

Универсальный интерфейс или делегат называется *вариантным*, если его универсальные параметры объявлены ковариантными или контрвариантными. Visual Basic позволяет вам создавать свои собственные вариантные интерфейсы и делегаты. Дополнительные сведения см. в разделах [Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) и [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).

## <a name="related-topics"></a>Связанные разделы

|Название|Описание|
|-----------|-----------------|
|[Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|В этом разделе описываются ковариация и контрвариация в универсальных интерфейсах, а также представлен список вариативных универсальных интерфейсов платформы .NET Framework.|
|[Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|Узнайте, как создавать ваши собственные вариантные интерфейсы.|
|[Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|Узнайте, как использовать поддержку ковариации и контрвариантности в интерфейсах <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601> для многократного использования кода.|
|[Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|Раздел описывает ковариацию и контрвариантность в универсальных и неуниверсальных делегатах, а также приводит список вариантных универсальных делегатов в платформе .NET Framework.|
|[Использование вариативности в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|Узнайте, как использовать поддержку ковариации и контрвариантности в неуниверсальных делегатах для сопоставления сигнатур методов с типами делегатов.|
|[Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|Узнайте, как использовать поддержку ковариации и контрвариантности в делегатах `Func` и `Action` для многократного использования кода.|
