---
title: "byte (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: 19
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
ms.openlocfilehash: 8ef7494e2a8a1463d37cff77d1dacebec8182b66
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="byte-c-reference"></a><span data-ttu-id="c8e4b-102">byte (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c8e4b-102">byte (C# Reference)</span></span>

<span data-ttu-id="c8e4b-103">Ключевое слово `byte` обозначает целочисленный тип данных, в котором хранятся значения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="c8e4b-104">Тип</span><span class="sxs-lookup"><span data-stu-id="c8e4b-104">Type</span></span>|<span data-ttu-id="c8e4b-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="c8e4b-105">Range</span></span>|<span data-ttu-id="c8e4b-106">Размер</span><span class="sxs-lookup"><span data-stu-id="c8e4b-106">Size</span></span>|<span data-ttu-id="c8e4b-107">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8e4b-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="c8e4b-108">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="c8e4b-108">0 to 255</span></span>|<span data-ttu-id="c8e4b-109">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="c8e4b-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="c8e4b-110">Литералы</span><span class="sxs-lookup"><span data-stu-id="c8e4b-110">Literals</span></span>  

 <span data-ttu-id="c8e4b-111">Переменную `byte` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="c8e4b-112">Если целочисленный литерал выходит за пределы диапазона `byte` (то есть если он меньше <xref:System.Byte.MinValue?displayProperty=fullName> или больше <xref:System.Byte.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=fullName> or greater than <xref:System.Byte.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="c8e4b-113">В следующем примере целые числа, равные 201 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `byte`.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
<span data-ttu-id="c8e4b-114">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]</span><span class="sxs-lookup"><span data-stu-id="c8e4b-114">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="c8e4b-115">Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c8e4b-116">У десятичных литералов префиксов нет.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c8e4b-117">Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="c8e4b-118">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]</span><span class="sxs-lookup"><span data-stu-id="c8e4b-118">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]</span></span>  
 
## <a name="conversions"></a><span data-ttu-id="c8e4b-119">Преобразования</span><span class="sxs-lookup"><span data-stu-id="c8e4b-119">Conversions</span></span>  
 <span data-ttu-id="c8e4b-120">Существует предопределенное неявное преобразование типа `byte` в типы [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="c8e4b-120">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="c8e4b-121">Невозможно неявным образом преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `byte`.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-121">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="c8e4b-122">Дополнительные сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="c8e4b-122">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="c8e4b-123">Рассмотрим, например, следующие две переменные `x` и `y` типа `byte`:</span><span class="sxs-lookup"><span data-stu-id="c8e4b-123">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="c8e4b-124">Следующий оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип `int`.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-124">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="c8e4b-125">Для устранения этой проблемы используйте приведение:</span><span class="sxs-lookup"><span data-stu-id="c8e4b-125">To fix this problem, use a cast:</span></span>  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="c8e4b-126">Однако можно использовать следующие операторы, в которых переменная назначения имеет такой же или больший размер при хранении:</span><span class="sxs-lookup"><span data-stu-id="c8e4b-126">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="c8e4b-127">Кроме того, неявного преобразования типов с плавающей запятой в тип `byte` не существует.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-127">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="c8e4b-128">Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:</span><span class="sxs-lookup"><span data-stu-id="c8e4b-128">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="c8e4b-129">При вызове перегруженных методов необходимо использовать приведение типов.</span><span class="sxs-lookup"><span data-stu-id="c8e4b-129">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="c8e4b-130">Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `byte` и [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="c8e4b-130">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="c8e4b-131">Использование приведения типа `byte` гарантирует вызов метода правильного типа, например:</span><span class="sxs-lookup"><span data-stu-id="c8e4b-131">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="c8e4b-132">Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="c8e4b-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="c8e4b-133">Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="c8e4b-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c8e4b-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c8e4b-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8e4b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c8e4b-135">See Also</span></span>  
 <span data-ttu-id="c8e4b-136"><xref:System.Byte></span><span class="sxs-lookup"><span data-stu-id="c8e4b-136"><xref:System.Byte></span></span>   
 <span data-ttu-id="c8e4b-137">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8e4b-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c8e4b-138">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8e4b-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c8e4b-139">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c8e4b-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c8e4b-140">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="c8e4b-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="c8e4b-141">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="c8e4b-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="c8e4b-142">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="c8e4b-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="c8e4b-143">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="c8e4b-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

