---
title: "char (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c6601a58804d6ecfcbedbc19da09560884e54e7f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="char-c-reference"></a><span data-ttu-id="fa7ef-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fa7ef-102">char (C# Reference)</span></span>
<span data-ttu-id="fa7ef-103">Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=fullName>, используемой .NET Framework для представления символа Юникода.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=fullName> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="fa7ef-104">Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="fa7ef-105">Символы в кодировке Юникода используются для представления большинства письменных языков в мире.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="fa7ef-106">Тип</span><span class="sxs-lookup"><span data-stu-id="fa7ef-106">Type</span></span>|<span data-ttu-id="fa7ef-107">Диапазон</span><span class="sxs-lookup"><span data-stu-id="fa7ef-107">Range</span></span>|<span data-ttu-id="fa7ef-108">Размер</span><span class="sxs-lookup"><span data-stu-id="fa7ef-108">Size</span></span>|<span data-ttu-id="fa7ef-109">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa7ef-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="fa7ef-110">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="fa7ef-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="fa7ef-111">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="fa7ef-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="fa7ef-112">Литералы</span><span class="sxs-lookup"><span data-stu-id="fa7ef-112">Literals</span></span>  
 <span data-ttu-id="fa7ef-113">Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="fa7ef-114">Также можно выполнить приведение целочисленных кодов символов.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="fa7ef-115">В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:</span><span class="sxs-lookup"><span data-stu-id="fa7ef-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 <span data-ttu-id="fa7ef-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fa7ef-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="fa7ef-117">Преобразования</span><span class="sxs-lookup"><span data-stu-id="fa7ef-117">Conversions</span></span>  
 <span data-ttu-id="fa7ef-118">Тип `char` может быть неявно преобразован в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="fa7ef-118">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="fa7ef-119">Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-119">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="fa7ef-120">Тип <xref:System.Char?displayProperty=fullName> предоставляет несколько статических методов для работы со значениями `char`.</span><span class="sxs-lookup"><span data-stu-id="fa7ef-120">The <xref:System.Char?displayProperty=fullName> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fa7ef-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fa7ef-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa7ef-122">См. также</span><span class="sxs-lookup"><span data-stu-id="fa7ef-122">See Also</span></span>  
 <span data-ttu-id="fa7ef-123"><xref:System.Char></span><span class="sxs-lookup"><span data-stu-id="fa7ef-123"><xref:System.Char></span></span>   
 <span data-ttu-id="fa7ef-124">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fa7ef-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fa7ef-126">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fa7ef-127">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-127">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="fa7ef-128">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-128">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="fa7ef-129">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-129">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="fa7ef-130">[Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-130">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="fa7ef-131">[Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa7ef-131">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="fa7ef-132">Строки</span><span class="sxs-lookup"><span data-stu-id="fa7ef-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

