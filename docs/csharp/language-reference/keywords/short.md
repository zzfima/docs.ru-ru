---
title: "short (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
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
ms.openlocfilehash: ab3ccfdeb8d8a67b5fcd60b1ad6eee4dcafc9691
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="short-c-reference"></a><span data-ttu-id="3399a-102">short (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3399a-102">short (C# Reference)</span></span>

<span data-ttu-id="3399a-103">Ключевое слово `short` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведены в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="3399a-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="3399a-104">Тип</span><span class="sxs-lookup"><span data-stu-id="3399a-104">Type</span></span>|<span data-ttu-id="3399a-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="3399a-105">Range</span></span>|<span data-ttu-id="3399a-106">Размер</span><span class="sxs-lookup"><span data-stu-id="3399a-106">Size</span></span>|<span data-ttu-id="3399a-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3399a-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="3399a-108">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="3399a-108">-32,768 to 32,767</span></span>|<span data-ttu-id="3399a-109">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="3399a-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="3399a-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="3399a-110">Literals</span></span>  

<span data-ttu-id="3399a-111">Переменную `short` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="3399a-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="3399a-112">Если целочисленный литерал выходит за пределы диапазона `short` (то есть если он меньше <xref:System.Int16.MinValue?displayProperty=fullName> или больше <xref:System.Int16.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="3399a-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=fullName> or greater than <xref:System.Int16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="3399a-113">В следующем примере целые числа, равные 1034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `short`.</span><span class="sxs-lookup"><span data-stu-id="3399a-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
<span data-ttu-id="3399a-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span><span class="sxs-lookup"><span data-stu-id="3399a-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="3399a-115">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="3399a-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="3399a-116">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="3399a-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="3399a-117">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3399a-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="3399a-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span><span class="sxs-lookup"><span data-stu-id="3399a-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="3399a-119">Разрешение перегрузки компилятора</span><span class="sxs-lookup"><span data-stu-id="3399a-119">Compiler overload resolution</span></span>

 <span data-ttu-id="3399a-120">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="3399a-120">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="3399a-121">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `short` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="3399a-121">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="3399a-122">Использование приведения типа `short` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="3399a-122">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="3399a-123">Преобразования</span><span class="sxs-lookup"><span data-stu-id="3399a-123">Conversions</span></span>  

 <span data-ttu-id="3399a-124">Существует предопределенное неявное преобразование типа `short` в тип [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="3399a-124">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="3399a-125">Нельзя неявно преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `short` (сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)).</span><span class="sxs-lookup"><span data-stu-id="3399a-125">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="3399a-126">Рассмотрим, например, следующие две переменные `x` и `y` типа `short`:</span><span class="sxs-lookup"><span data-stu-id="3399a-126">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="3399a-127">Приведенный ниже оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="3399a-127">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="3399a-128">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="3399a-128">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="3399a-129">Также можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="3399a-129">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="3399a-130">Неявного преобразования типов с плавающей запятой в тип `short` не существует.</span><span class="sxs-lookup"><span data-stu-id="3399a-130">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="3399a-131">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="3399a-131">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="3399a-132">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="3399a-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="3399a-133">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="3399a-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3399a-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3399a-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3399a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3399a-135">See Also</span></span>  
 <span data-ttu-id="3399a-136"><xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="3399a-136"><xref:System.Int16></span></span>   
 <span data-ttu-id="3399a-137">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3399a-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3399a-138">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3399a-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3399a-139">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3399a-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3399a-140">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3399a-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="3399a-141">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3399a-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="3399a-142">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="3399a-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="3399a-143">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="3399a-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

