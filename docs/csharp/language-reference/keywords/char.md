---
title: "char (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords: char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 41f672e9b12481fa5cce78015e95d2c5245a26db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="char-c-reference"></a><span data-ttu-id="2fc70-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2fc70-102">char (C# Reference)</span></span>
<span data-ttu-id="2fc70-103">Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=nameWithType>, используемой .NET Framework для представления символа Юникода.</span><span class="sxs-lookup"><span data-stu-id="2fc70-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="2fc70-104">Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.</span><span class="sxs-lookup"><span data-stu-id="2fc70-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="2fc70-105">Символы в кодировке Юникода используются для представления большинства письменных языков в мире.</span><span class="sxs-lookup"><span data-stu-id="2fc70-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="2fc70-106">Тип</span><span class="sxs-lookup"><span data-stu-id="2fc70-106">Type</span></span>|<span data-ttu-id="2fc70-107">Диапазон</span><span class="sxs-lookup"><span data-stu-id="2fc70-107">Range</span></span>|<span data-ttu-id="2fc70-108">Размер</span><span class="sxs-lookup"><span data-stu-id="2fc70-108">Size</span></span>|<span data-ttu-id="2fc70-109">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2fc70-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="2fc70-110">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="2fc70-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="2fc70-111">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="2fc70-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="2fc70-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="2fc70-112">Literals</span></span>  
 <span data-ttu-id="2fc70-113">Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода.</span><span class="sxs-lookup"><span data-stu-id="2fc70-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="2fc70-114">Также можно выполнить приведение целочисленных кодов символов.</span><span class="sxs-lookup"><span data-stu-id="2fc70-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="2fc70-115">В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:</span><span class="sxs-lookup"><span data-stu-id="2fc70-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a><span data-ttu-id="2fc70-116">Преобразования</span><span class="sxs-lookup"><span data-stu-id="2fc70-116">Conversions</span></span>  
 <span data-ttu-id="2fc70-117">Тип `char` может быть неявно преобразован в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="2fc70-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="2fc70-118">Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="2fc70-118">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="2fc70-119">Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.</span><span class="sxs-lookup"><span data-stu-id="2fc70-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2fc70-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2fc70-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2fc70-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2fc70-121">See Also</span></span>  
 <xref:System.Char>  
 [<span data-ttu-id="2fc70-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2fc70-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2fc70-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2fc70-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2fc70-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="2fc70-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2fc70-125">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="2fc70-125">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="2fc70-126">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="2fc70-126">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="2fc70-127">Таблица неявных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="2fc70-127">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="2fc70-128">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="2fc70-128">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="2fc70-129">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="2fc70-129">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="2fc70-130">Строки</span><span class="sxs-lookup"><span data-stu-id="2fc70-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
