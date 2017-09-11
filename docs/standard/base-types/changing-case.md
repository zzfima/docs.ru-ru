---
title: "Смена регистра"
description: "Смена регистра"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a><span data-ttu-id="4f8c8-104">Смена регистра</span><span class="sxs-lookup"><span data-stu-id="4f8c8-104">Changing case</span></span>

<span data-ttu-id="4f8c8-105">При написании приложения, которое принимает входные данные от пользователя, невозможно предугадать, какой регистр будет использоваться для ввода данных.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-105">If you write an application that accepts input from a user, you can never be sure what case he or she will use to enter the data.</span></span> <span data-ttu-id="4f8c8-106">Часто требуется обеспечить согласованность регистра строк, особенно если они отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-106">Often, you want strings to be cased consistently, particularly if you are displaying them in the user interface.</span></span> <span data-ttu-id="4f8c8-107">В таблице ниже описаны два метода изменения регистра.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-107">The following table describes two case-changing methods.</span></span>

<span data-ttu-id="4f8c8-108">Имя метода</span><span class="sxs-lookup"><span data-stu-id="4f8c8-108">Method name</span></span> | <span data-ttu-id="4f8c8-109">Применение</span><span class="sxs-lookup"><span data-stu-id="4f8c8-109">Use</span></span>
----------- | ---
[<span data-ttu-id="4f8c8-110">String.ToUpper</span><span class="sxs-lookup"><span data-stu-id="4f8c8-110">String.ToUpper</span></span>](xref:System.String.ToUpper) | <span data-ttu-id="4f8c8-111">Преобразует все символы в строке в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-111">Converts all characters in a string to uppercase.</span></span>
[<span data-ttu-id="4f8c8-112">String.ToLower</span><span class="sxs-lookup"><span data-stu-id="4f8c8-112">String.ToLower</span></span>](xref:System.String.ToLower) | <span data-ttu-id="4f8c8-113">Преобразует все символы в строке в нижний регистр.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-113">Converts all characters in a string to lowercase.</span></span>

> [!WARNING]  
> <span data-ttu-id="4f8c8-114">Обратите внимание, что методы `String.ToUpper` и `String.ToLower` не следует использовать для преобразования строк с целью их сравнения или проверки на равенство.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-114">Note that the `String.ToUpper` and `String.ToLower` methods should not be used to convert strings in order to compare them or test them for equality.</span></span> 

## <a name="comparing-strings-of-mixed-case"></a><span data-ttu-id="4f8c8-115">Сравнение строк, содержащих символы в разных регистрах</span><span class="sxs-lookup"><span data-stu-id="4f8c8-115">Comparing strings of mixed case</span></span>

<span data-ttu-id="4f8c8-116">Чтобы сравнить строки, содержащие символы в разных регистрах для их упорядочения, вызовите одну из перегрузок метода [String](xref:System) `Equals` с параметром *comparisonType* и укажите значение [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) для аргумента *comparisonType*.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-116">To compare strings of mixed case to determine whether they are equal, their, call one of the overloads of the [String](xref:System) `Equals` method with a *comparisonType* parameter, and provide a value of either [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for the *comparisonType* argument.</span></span> 

<span data-ttu-id="4f8c8-117">Дополнительные сведения см. в разделе [Рекомендации по использованию строк](best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="4f8c8-117">For more information, see [Best Practices for Using Strings](best-practices.md).</span></span> 

## <a name="toupper"></a><span data-ttu-id="4f8c8-118">ToUpper</span><span class="sxs-lookup"><span data-stu-id="4f8c8-118">ToUpper</span></span>

<span data-ttu-id="4f8c8-119">Метод [String.ToUpper](xref:System.String.ToUpper) преобразует все символы в строке в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-119">The [String.ToUpper](xref:System.String.ToUpper) method changes all characters in a string to uppercase.</span></span> <span data-ttu-id="4f8c8-120">В примере ниже смешанный регистр строки "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="4f8c8-120">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="4f8c8-121">изменяется на верхний.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-121">from mixed case to uppercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a><span data-ttu-id="4f8c8-122">ToLower</span><span class="sxs-lookup"><span data-stu-id="4f8c8-122">ToLower</span></span>

<span data-ttu-id="4f8c8-123">Метод [String.ToLower](xref:System.String.ToLower) аналогичен предыдущему методу, однако преобразует все символы в строке в нижний регистр.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-123">The [String.ToLower](xref:System.String.ToLower) method is similar to the previous method, but instead converts all the characters in a string to lowercase.</span></span> <span data-ttu-id="4f8c8-124">В примере ниже смешанный регистр строки "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="4f8c8-124">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="4f8c8-125">изменяется на нижний.</span><span class="sxs-lookup"><span data-stu-id="4f8c8-125">to lowercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a><span data-ttu-id="4f8c8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4f8c8-126">See Also</span></span>

[<span data-ttu-id="4f8c8-127">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="4f8c8-127">Basic string operations</span></span>](basic-string-operations.md)

