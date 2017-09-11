---
title: "Заполнение строк"
description: "Заполнение строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bc3cc9028b232cc2ba6ca3130c4bdb261c4a0a42
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="padding-strings"></a><span data-ttu-id="0e46b-104">Заполнение строк</span><span class="sxs-lookup"><span data-stu-id="0e46b-104">Padding strings</span></span>

<span data-ttu-id="0e46b-105">Для создания новой строки, состоящей из исходной строки, дополненной знаками до указанной общей длины с начала или с конца, следует использовать один из следующих методов класса [System.String](xref:System.String).</span><span class="sxs-lookup"><span data-stu-id="0e46b-105">Use one of the following [System.String](xref:System.String) methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="0e46b-106">В качестве заполняющего знака, который, соответственно, будет повторяться либо справа, либо слева, может использоваться пробел или знак, заданный в явной форме.</span><span class="sxs-lookup"><span data-stu-id="0e46b-106">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>

<span data-ttu-id="0e46b-107">Имя метода</span><span class="sxs-lookup"><span data-stu-id="0e46b-107">Method name</span></span> | <span data-ttu-id="0e46b-108">Применение</span><span class="sxs-lookup"><span data-stu-id="0e46b-108">Use</span></span>
----------- | ---
<span data-ttu-id="0e46b-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="0e46b-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span></span> | <span data-ttu-id="0e46b-110">Дополняет строку до указанной общей длины знаками с начала.</span><span class="sxs-lookup"><span data-stu-id="0e46b-110">Pads a string with leading characters to a specified total length.</span></span>
<span data-ttu-id="0e46b-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="0e46b-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span></span> | <span data-ttu-id="0e46b-112">Дополняет строку до указанной общей длины знаками с конца.</span><span class="sxs-lookup"><span data-stu-id="0e46b-112">Pads a string with trailing characters to a specified total length.</span></span>

## <a name="padleft"></a><span data-ttu-id="0e46b-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="0e46b-113">PadLeft</span></span>

<span data-ttu-id="0e46b-114">Метод [String.PadLeft](xref:System.String.PadLeft(System.Int32)) создает новую строку, присоединяя к исходной строке знаки с начала в количестве, необходимом для достижения указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="0e46b-114">The [String.PadLeft](xref:System.String.PadLeft(System.Int32)) method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="0e46b-115">В методе [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) в качестве заполняющих знаков используются пробелы, а метод [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) позволяет задать заполняющий знак в явной форме.</span><span class="sxs-lookup"><span data-stu-id="0e46b-115">The [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) method uses white space as the padding character and the [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="0e46b-116">В следующем примере кода метод [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) используется для создания новой строки длиной в двадцать знаков.</span><span class="sxs-lookup"><span data-stu-id="0e46b-116">The following code example uses the [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="0e46b-117">Этот пример выводит на консоль значение "`--------Hello World!`".</span><span class="sxs-lookup"><span data-stu-id="0e46b-117">The example displays "`--------Hello World!`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a><span data-ttu-id="0e46b-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="0e46b-118">PadRight</span></span>

<span data-ttu-id="0e46b-119">Метод [String.PadRight](xref:System.String.PadRight(System.Int32)) создает новую строку, присоединяя к исходной строке знаки с конца в количестве, необходимом для достижения указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="0e46b-119">The [String.PadRight](xref:System.String.PadRight(System.Int32)) method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="0e46b-120">В методе [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) в качестве заполняющих знаков используются пробелы, а метод [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) позволяет задать заполняющий знак в явной форме.</span><span class="sxs-lookup"><span data-stu-id="0e46b-120">The [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) method uses white space as the padding character and the [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="0e46b-121">В следующем примере кода метод [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) используется для создания новой строки длиной в двадцать знаков.</span><span class="sxs-lookup"><span data-stu-id="0e46b-121">The following code example uses the [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="0e46b-122">Этот пример выводит на консоль значение "`Hello World!--------`".</span><span class="sxs-lookup"><span data-stu-id="0e46b-122">The example displays "`Hello World!--------`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a><span data-ttu-id="0e46b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0e46b-123">See Also</span></span>

[<span data-ttu-id="0e46b-124">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="0e46b-124">Basic string operations</span></span>](basic-string-operations.md)


