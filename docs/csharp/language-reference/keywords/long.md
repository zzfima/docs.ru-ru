---
title: "long (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
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
ms.openlocfilehash: 5f7d2d6a3d5781b4e120b8399c7206d4429dd98e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="long-c-reference"></a><span data-ttu-id="0d9db-102">long (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0d9db-102">long (C# Reference)</span></span>

<span data-ttu-id="0d9db-103">`long` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="0d9db-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="0d9db-104">Тип</span><span class="sxs-lookup"><span data-stu-id="0d9db-104">Type</span></span>|<span data-ttu-id="0d9db-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="0d9db-105">Range</span></span>|<span data-ttu-id="0d9db-106">Размер</span><span class="sxs-lookup"><span data-stu-id="0d9db-106">Size</span></span>|<span data-ttu-id="0d9db-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d9db-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="0d9db-108">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="0d9db-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="0d9db-109">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="0d9db-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="0d9db-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="0d9db-110">Literals</span></span> 

<span data-ttu-id="0d9db-111">Переменную `long` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="0d9db-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="0d9db-112">В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `long`.</span><span class="sxs-lookup"><span data-stu-id="0d9db-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
<span data-ttu-id="0d9db-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span><span class="sxs-lookup"><span data-stu-id="0d9db-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="0d9db-114">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="0d9db-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="0d9db-115">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="0d9db-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="0d9db-116">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0d9db-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="0d9db-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="0d9db-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="0d9db-118">Целочисленные литералы могут также содержать суффикс, обозначающий тип.</span><span class="sxs-lookup"><span data-stu-id="0d9db-118">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="0d9db-119">Суффикс `L` обозначает `long`.</span><span class="sxs-lookup"><span data-stu-id="0d9db-119">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="0d9db-120">В следующем примере суффикс `L` используется для обозначения длинного целого числа:</span><span class="sxs-lookup"><span data-stu-id="0d9db-120">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="0d9db-121">Также в качестве суффикса можно использовать строчную букву "I".</span><span class="sxs-lookup"><span data-stu-id="0d9db-121">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="0d9db-122">Однако при этом выдается предупреждение компилятора, так как букву "l" легко перепутать с цифрой "1".</span><span class="sxs-lookup"><span data-stu-id="0d9db-122">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="0d9db-123">Для ясности используйте "L".</span><span class="sxs-lookup"><span data-stu-id="0d9db-123">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="0d9db-124">При использовании суффикса `L` тип целочисленного литерала определяется как `long` или [ulong](../../../csharp/language-reference/keywords/ulong.md) в зависимости от его размера.</span><span class="sxs-lookup"><span data-stu-id="0d9db-124">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="0d9db-125">В данном случае это тип `long`, поскольку его диапазон меньше, чем требуется для типа [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="0d9db-125">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="0d9db-126">Обычно суффикс используется для вызова перегруженных методов.</span><span class="sxs-lookup"><span data-stu-id="0d9db-126">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="0d9db-127">Например, следующие перегруженные методы имеют параметры типов `long` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="0d9db-127">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="0d9db-128">Суффикс `L` обеспечивает вызов нужной перегрузки:</span><span class="sxs-lookup"><span data-stu-id="0d9db-128">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="0d9db-129">Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:</span><span class="sxs-lookup"><span data-stu-id="0d9db-129">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="0d9db-130">int</span><span class="sxs-lookup"><span data-stu-id="0d9db-130">int</span></span>](int.md)
2. [<span data-ttu-id="0d9db-131">uint</span><span class="sxs-lookup"><span data-stu-id="0d9db-131">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="0d9db-132">ulong</span><span class="sxs-lookup"><span data-stu-id="0d9db-132">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="0d9db-133">Литерал 4294967296 в предыдущем примере имеет тип `long`, поскольку выходит за пределы типа [uint](../../../csharp/language-reference/keywords/uint.md) (объемы хранения целочисленных типов см. в [таблице целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)).</span><span class="sxs-lookup"><span data-stu-id="0d9db-133">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="0d9db-134">Тип `long` можно использовать с другими целочисленными типами в том же выражении, в случае чего выражение вычисляется как `long` (или [bool](../../../csharp/language-reference/keywords/bool.md) для реляционных или логических выражений).</span><span class="sxs-lookup"><span data-stu-id="0d9db-134">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="0d9db-135">Например, следующее выражение вычисляется как `long`:</span><span class="sxs-lookup"><span data-stu-id="0d9db-135">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="0d9db-136">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="0d9db-136">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="0d9db-137">Преобразования</span><span class="sxs-lookup"><span data-stu-id="0d9db-137">Conversions</span></span>  
 <span data-ttu-id="0d9db-138">Существует предопределенное неявное преобразование типа `long` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="0d9db-138">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="0d9db-139">В противном случае необходимо использовать приведение.</span><span class="sxs-lookup"><span data-stu-id="0d9db-139">Otherwise a cast must be used.</span></span> <span data-ttu-id="0d9db-140">Например, следующий оператор вызывает ошибку компиляции без явного приведения:</span><span class="sxs-lookup"><span data-stu-id="0d9db-140">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="0d9db-141">Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в `long`.</span><span class="sxs-lookup"><span data-stu-id="0d9db-141">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="0d9db-142">Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `long` не существует.</span><span class="sxs-lookup"><span data-stu-id="0d9db-142">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="0d9db-143">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="0d9db-143">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d9db-144">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0d9db-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d9db-145">См. также</span><span class="sxs-lookup"><span data-stu-id="0d9db-145">See Also</span></span>  
 <span data-ttu-id="0d9db-146"><xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="0d9db-146"><xref:System.Int64></span></span>   
 <span data-ttu-id="0d9db-147">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d9db-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0d9db-148">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d9db-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0d9db-149">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d9db-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0d9db-150">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="0d9db-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="0d9db-151">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="0d9db-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="0d9db-152">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="0d9db-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="0d9db-153">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="0d9db-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

