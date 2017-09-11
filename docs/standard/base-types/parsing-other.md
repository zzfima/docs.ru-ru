---
title: "Анализ других строк в .NET"
description: "Анализ других строк в .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: db80cc5f37e814f224ff76b14a906bb4d41064fb
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="2df46-104">Анализ других строк в .NET</span><span class="sxs-lookup"><span data-stu-id="2df46-104">Parsing other strings in .NET</span></span>

<span data-ttu-id="2df46-105">Кроме числовых строк и строк [DateTime](xref:System.DateTime) можно также разбирать строки, представляющие типы [Char](xref:System.Char), [Boolean](xref:System.Boolean) и [Enum](xref:System.Enum), в типы данных.</span><span class="sxs-lookup"><span data-stu-id="2df46-105">In addition to numeric and [DateTime](xref:System.DateTime) strings, you can also parse strings that represent the types [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) into data types.</span></span>

## <a name="char"></a><span data-ttu-id="2df46-106">Char</span><span class="sxs-lookup"><span data-stu-id="2df46-106">Char</span></span>

<span data-ttu-id="2df46-107">Метод статического анализа, связанный с типом данных[Char](xref:System.Char), полезен для преобразования строки, содержащей один символ, в его значение в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="2df46-107">The static parse method associated with the [Char](xref:System.Char) data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="2df46-108">В следующем примере кода выполняется разбор строки в символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="2df46-108">The following code example parses a string into a Unicode character.</span></span>

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a><span data-ttu-id="2df46-109">Boolean</span><span class="sxs-lookup"><span data-stu-id="2df46-109">Boolean</span></span>

<span data-ttu-id="2df46-110">Тип данных [Boolean](xref:System.Boolean) содержит метод [Parse](xref:System.Boolean.Parse(System.String)), который можно использовать для преобразования строки, представляющей значение `Boolean`, в реальный тип `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="2df46-110">The [Boolean](xref:System.Boolean) data type contains a [Parse](xref:System.Boolean.Parse(System.String)) method that you can use to convert a string that represents a `Boolean` value into an actual `Boolean` type.</span></span> <span data-ttu-id="2df46-111">Этот метод не учитывает регистр и может успешно анализировать строку, содержащую значения "True" или "False".</span><span class="sxs-lookup"><span data-stu-id="2df46-111">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="2df46-112">Метод `Parse`, связанный с типом `Boolean`, может также анализировать строки, окруженные пробелами.</span><span class="sxs-lookup"><span data-stu-id="2df46-112">The `Parse` method associated with the `Boolean` type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="2df46-113">Если передается любая другая строка, создается исключение [FormatException](xref:System.FormatException).</span><span class="sxs-lookup"><span data-stu-id="2df46-113">If any other string is passed, a [FormatException](xref:System.FormatException) is thrown.</span></span>

<span data-ttu-id="2df46-114">В следующем примере кода показано использование метода `Parse` для преобразования строки в значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="2df46-114">The following code example uses the `Parse` method to convert a string into a `Boolean` value.</span></span>

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a><span data-ttu-id="2df46-115">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2df46-115">Enumeration</span></span>

<span data-ttu-id="2df46-116">Статический метод [Parse](xref:System.Enum.Parse(System.Type,System.String)) можно использовать, чтобы инициализировать значение строки типом перечисления.</span><span class="sxs-lookup"><span data-stu-id="2df46-116">You can use the static [Parse](xref:System.Enum.Parse(System.Type,System.String)) method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="2df46-117">Этот метод принимает тип перечисления для разбора, анализируемую строку и необязательный флаг `Boolean`, указывающий, будет ли при анализе учитываться регистр.</span><span class="sxs-lookup"><span data-stu-id="2df46-117">This method accepts the enumeration type you are parsing, the string to parse, and an optional `Boolean` flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="2df46-118">Анализируемая строка может содержать несколько значений, разделенных запятыми; перед этими значениями или после них могут быть один или несколько пробелов.</span><span class="sxs-lookup"><span data-stu-id="2df46-118">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="2df46-119">Если строка содержит несколько значений, то возвращаемый объект будет содержать сочетание заданных значений, полученное с использованием побитовой операции OR.</span><span class="sxs-lookup"><span data-stu-id="2df46-119">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>

<span data-ttu-id="2df46-120">В следующем примере показано использование метода `Parse` для преобразования строкового представления в значение перечисления.</span><span class="sxs-lookup"><span data-stu-id="2df46-120">The following example uses the `Parse` method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="2df46-121">Перечислению [DayOfWeek](xref:System.DayOfWeek) присваивается значение Thursday из строки.</span><span class="sxs-lookup"><span data-stu-id="2df46-121">The [DayOfWeek](xref:System.DayOfWeek) enumeration is initialized to Thursday from a string.</span></span>

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a><span data-ttu-id="2df46-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2df46-122">See Also</span></span>

[<span data-ttu-id="2df46-123">Анализ строк в .NET</span><span class="sxs-lookup"><span data-stu-id="2df46-123">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="2df46-124">Типы форматирования в .NET</span><span class="sxs-lookup"><span data-stu-id="2df46-124">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="2df46-125">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="2df46-125">Type conversion in .NET</span></span>](type-conversion.md)


