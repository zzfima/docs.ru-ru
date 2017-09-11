---
title: "float (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
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
ms.openlocfilehash: 2f1fb02f84de504112eee826dbee1275fa3ccb7a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="float-c-reference"></a><span data-ttu-id="e7617-102">float (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e7617-102">float (C# Reference)</span></span>
<span data-ttu-id="e7617-103">Ключевое слово `float` обозначает простой тип, в котором хранятся 32-разрядные значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e7617-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="e7617-104">В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `float`.</span><span class="sxs-lookup"><span data-stu-id="e7617-104">The following table shows the precision and approximate range for the `float` type.</span></span>  
  
|<span data-ttu-id="e7617-105">Тип</span><span class="sxs-lookup"><span data-stu-id="e7617-105">Type</span></span>|<span data-ttu-id="e7617-106">Приблизительный диапазон значений</span><span class="sxs-lookup"><span data-stu-id="e7617-106">Approximate range</span></span>|<span data-ttu-id="e7617-107">Точность</span><span class="sxs-lookup"><span data-stu-id="e7617-107">Precision</span></span>|<span data-ttu-id="e7617-108">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7617-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="e7617-109">От -3.4 × 10<sup>38</sup>до +3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="e7617-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span></span>|<span data-ttu-id="e7617-110">7 знака</span><span class="sxs-lookup"><span data-stu-id="e7617-110">7 digits</span></span>|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="e7617-111">Литералы</span><span class="sxs-lookup"><span data-stu-id="e7617-111">Literals</span></span>  
 <span data-ttu-id="e7617-112">По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="e7617-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="e7617-113">Таким образом, для инициализации переменной с плавающей запятой следует использовать суффикс `f` или `F`, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="e7617-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>  
  
```csharp
float x = 3.5F;  
```
  
 <span data-ttu-id="e7617-114">Если этот суффикс не указан в предыдущем объявлении, вы получите ошибку компиляции, поскольку пытаетесь сохранить значение [double](double.md) в переменную `float`.</span><span class="sxs-lookup"><span data-stu-id="e7617-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="e7617-115">Преобразования</span><span class="sxs-lookup"><span data-stu-id="e7617-115">Conversions</span></span>  
 <span data-ttu-id="e7617-116">В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e7617-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="e7617-117">В этом случае целочисленные типы преобразуются в типы с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="e7617-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="e7617-118">Выражение вычисляется по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="e7617-118">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="e7617-119">Если одним из типов с плавающей запятой является [double](double.md), то выражение оценивается в реляционных или логических выражениях как [double](double.md) или [bool](bool.md).</span><span class="sxs-lookup"><span data-stu-id="e7617-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md) or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="e7617-120">Если в выражении нет типа [double](double.md), выражение оценивается в реляционных или логических выражениях как `float` или [bool](bool.md).</span><span class="sxs-lookup"><span data-stu-id="e7617-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float` or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="e7617-121">Выражение с плавающей запятой может содержать следующие наборы значений:</span><span class="sxs-lookup"><span data-stu-id="e7617-121">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="e7617-122">Положительный и отрицательный ноль</span><span class="sxs-lookup"><span data-stu-id="e7617-122">Positive and negative zero</span></span>  
  
-   <span data-ttu-id="e7617-123">Положительная и отрицательная бесконечность</span><span class="sxs-lookup"><span data-stu-id="e7617-123">Positive and negative infinity</span></span>  
  
-   <span data-ttu-id="e7617-124">Нечисловое значение (NaN)</span><span class="sxs-lookup"><span data-stu-id="e7617-124">Not-a-Number value (NaN)</span></span>  
  
-   <span data-ttu-id="e7617-125">Конечный набор ненулевых значений</span><span class="sxs-lookup"><span data-stu-id="e7617-125">The finite set of nonzero values</span></span>  
  
 <span data-ttu-id="e7617-126">Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).</span><span class="sxs-lookup"><span data-stu-id="e7617-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7617-127">Пример</span><span class="sxs-lookup"><span data-stu-id="e7617-127">Example</span></span>  
 <span data-ttu-id="e7617-128">В следующем примере [int](int.md), [short](short.md) и `float` включены в математическое выражение и дают результат `float`.</span><span class="sxs-lookup"><span data-stu-id="e7617-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="e7617-129">(Помните, что `float` — это псевдоним для типа <xref:System.Single?displayProperty=fullName>.) Обратите внимание, что в выражении нет типа [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="e7617-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=fullName> type.) Notice that there is no [double](double.md) in the expression.</span></span>  
  
 <span data-ttu-id="e7617-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7617-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e7617-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e7617-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7617-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e7617-132">See Also</span></span>  
 <span data-ttu-id="e7617-133"><xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="e7617-133"><xref:System.Single></span></span>   
 <span data-ttu-id="e7617-134">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e7617-135">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e7617-136">[Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-136">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="e7617-137">[Ключевые слова в C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-137">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="e7617-138">[Таблица целых типов](integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-138">[Integral Types Table](integral-types-table.md) </span></span>  
 <span data-ttu-id="e7617-139">[Таблица встроенных типов](built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-139">[Built-In Types Table](built-in-types-table.md) </span></span>  
 <span data-ttu-id="e7617-140">[Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="e7617-140">[Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="e7617-141">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="e7617-141">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)

