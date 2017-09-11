---
title: "double (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d5588f8391157fb56a5e5067bb8e11f9269fe733
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="double-c-reference"></a><span data-ttu-id="e8f4d-102">double (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e8f4d-102">double (C# Reference)</span></span>
<span data-ttu-id="e8f4d-103">Ключевое слово `double` обозначает простой тип, используемый для хранения 64-разрядных значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="e8f4d-104">В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-104">The following table shows the precision and approximate range for the `double` type.</span></span>  
  
|<span data-ttu-id="e8f4d-105">Тип</span><span class="sxs-lookup"><span data-stu-id="e8f4d-105">Type</span></span>|<span data-ttu-id="e8f4d-106">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="e8f4d-106">Approximate range</span></span>|<span data-ttu-id="e8f4d-107">Точность</span><span class="sxs-lookup"><span data-stu-id="e8f4d-107">Precision</span></span>|<span data-ttu-id="e8f4d-108">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e8f4d-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|<span data-ttu-id="e8f4d-109">от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="e8f4d-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="e8f4d-110">15–16 знаков</span><span class="sxs-lookup"><span data-stu-id="e8f4d-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="e8f4d-111">Литералы</span><span class="sxs-lookup"><span data-stu-id="e8f4d-111">Literals</span></span>  
 <span data-ttu-id="e8f4d-112">По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как `double`.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="e8f4d-113">Если необходимо, чтобы целое число обрабатывалось как `double`, следует использовать суффикс d или D, например:</span><span class="sxs-lookup"><span data-stu-id="e8f4d-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a><span data-ttu-id="e8f4d-114">Преобразования</span><span class="sxs-lookup"><span data-stu-id="e8f4d-114">Conversions</span></span>  
 <span data-ttu-id="e8f4d-115">В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="e8f4d-116">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="e8f4d-117">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="e8f4d-117">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="e8f4d-118">Если одним из типов с плавающей запятой является `double`, результатом выражения является тип `double` или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных либо логических выражениях.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="e8f4d-119">Если в выражении не используется тип `double`, результатом выражения является тип [float](../../../csharp/language-reference/keywords/float.md) или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных либо логических выражениях.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="e8f4d-120">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="e8f4d-120">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="e8f4d-121">положительный и отрицательный нуль;</span><span class="sxs-lookup"><span data-stu-id="e8f4d-121">Positive and negative zero.</span></span>  
  
-   <span data-ttu-id="e8f4d-122">положительная и отрицательная бесконечность;</span><span class="sxs-lookup"><span data-stu-id="e8f4d-122">Positive and negative infinity.</span></span>  
  
-   <span data-ttu-id="e8f4d-123">нечисловое значение (NaN);</span><span class="sxs-lookup"><span data-stu-id="e8f4d-123">Not-a-Number value (NaN).</span></span>  
  
-   <span data-ttu-id="e8f4d-124">конечный набор ненулевых значений.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-124">The finite set of nonzero values.</span></span>  
  
 <span data-ttu-id="e8f4d-125">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).</span><span class="sxs-lookup"><span data-stu-id="e8f4d-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8f4d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="e8f4d-126">Example</span></span>  
 <span data-ttu-id="e8f4d-127">В следующем примере складываются значения, имеющие типы [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) и `double`. Получается результат, имеющий тип `double`.</span><span class="sxs-lookup"><span data-stu-id="e8f4d-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>  
  
 <span data-ttu-id="e8f4d-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8f4d-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e8f4d-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e8f4d-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8f4d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e8f4d-130">See Also</span></span>  
 <span data-ttu-id="e8f4d-131">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e8f4d-132">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e8f4d-133">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e8f4d-134">[Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-134">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="e8f4d-135">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-135">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="e8f4d-136">[Таблица типов с плавающей запятой](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-136">[Floating-Point Types Table](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span></span>  
 <span data-ttu-id="e8f4d-137">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8f4d-137">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="e8f4d-138">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="e8f4d-138">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

