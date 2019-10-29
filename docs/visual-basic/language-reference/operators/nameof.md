---
title: Оператор NameOf — Visual Basic
description: Узнайте, как использовать оператор NameOf в Visual Basic
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 8416bb1a1715c1c37b62cac6a9e0b427a9c72547
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041355"
---
# <a name="nameof-operator---visual-basic"></a>Оператор NameOf — Visual Basic

Оператор `NameOf` получает имя, тип или член переменной в качестве строковой константы:

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

Оператор `NameOf` вычисляется во время компиляции и это не влияет на время выполнения.

С помощью оператора `NameOf` можно сделать код проверки аргументов более удобным:

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

Оператор `NameOf` доступен в Visual Basic 14 и более поздних версий.

## <a name="see-also"></a>См. также

- [Справочник по языку Visual Basic](../index.md)
- [Операторы (Visual Basic)](index.md)
