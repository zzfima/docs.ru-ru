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
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="4fd27-103">Оператор NameOf — Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4fd27-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="4fd27-104">Оператор `NameOf` получает имя, тип или член переменной в качестве строковой константы:</span><span class="sxs-lookup"><span data-stu-id="4fd27-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

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

<span data-ttu-id="4fd27-105">Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="4fd27-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="4fd27-106">Оператор `NameOf` вычисляется во время компиляции и это не влияет на время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4fd27-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="4fd27-107">С помощью оператора `NameOf` можно сделать код проверки аргументов более удобным:</span><span class="sxs-lookup"><span data-stu-id="4fd27-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

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

<span data-ttu-id="4fd27-108">Оператор `NameOf` доступен в Visual Basic 14 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4fd27-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fd27-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4fd27-109">See also</span></span>

- [<span data-ttu-id="4fd27-110">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4fd27-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="4fd27-111">Операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fd27-111">Operators (Visual Basic)</span></span>](index.md)
