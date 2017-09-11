---
title: "checked (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
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
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-reference"></a><span data-ttu-id="0125f-102">checked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0125f-102">checked (C# Reference)</span></span>
<span data-ttu-id="0125f-103">Ключевое слово `checked` используется для явного включения проверки переполнения при выполнении арифметических операций и преобразований с данными целого типа.</span><span class="sxs-lookup"><span data-stu-id="0125f-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="0125f-104">По умолчанию выражение, содержащее только константные значения, вызывает ошибку компилятора в том случае, если результат его вычисления выходит за допустимые пределы значений конечного типа.</span><span class="sxs-lookup"><span data-stu-id="0125f-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="0125f-105">Если выражение содержит одно или несколько неконстантных значений, компилятор не выполняет проверку переполнения.</span><span class="sxs-lookup"><span data-stu-id="0125f-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="0125f-106">Вычисление выражения, присвоенного переменной `i2` в приведенном ниже примере, не вызывает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="0125f-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 <span data-ttu-id="0125f-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0125f-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span></span>  
  
 <span data-ttu-id="0125f-108">По умолчанию эти неконстантные выражения также не проверяются на переполнение во время выполнения, и они не создают исключений переполнения.</span><span class="sxs-lookup"><span data-stu-id="0125f-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="0125f-109">В предыдущем примере в качестве суммы двух положительных целых чисел выводится значение -2 147 483 639.</span><span class="sxs-lookup"><span data-stu-id="0125f-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="0125f-110">Проверку переполнения можно включить посредством параметров компилятора, настройки среды или использования ключевого слова `checked`.</span><span class="sxs-lookup"><span data-stu-id="0125f-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="0125f-111">В следующих примерах демонстрируется использование выражения `checked` или блока `checked` для обнаружения переполнения, возникающего в результате предыдущего сложения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0125f-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="0125f-112">В обоих примерах создается исключение переполнения.</span><span class="sxs-lookup"><span data-stu-id="0125f-112">Both examples raise an overflow exception.</span></span>  
  
 <span data-ttu-id="0125f-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0125f-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span></span>  
  
 <span data-ttu-id="0125f-114">Для запрета проверки переполнения можно использовать ключевое слово [unchecked](../../../csharp/language-reference/keywords/unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="0125f-114">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0125f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="0125f-115">Example</span></span>  
 <span data-ttu-id="0125f-116">В этом примере демонстрируется включение проверки переполнения во время выполнения посредством ключевого слова `checked`.</span><span class="sxs-lookup"><span data-stu-id="0125f-116">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 <span data-ttu-id="0125f-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="0125f-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0125f-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0125f-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0125f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0125f-119">See Also</span></span>  
 <span data-ttu-id="0125f-120">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0125f-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0125f-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0125f-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0125f-122">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0125f-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0125f-123">[Операторы checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="0125f-123">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="0125f-124">unchecked</span><span class="sxs-lookup"><span data-stu-id="0125f-124">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)

