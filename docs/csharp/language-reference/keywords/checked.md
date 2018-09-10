---
title: Ключевое слово checked (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 892b24b0283314f5aded0405df55a93069cf91e2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505259"
---
# <a name="checked-c-reference"></a><span data-ttu-id="42fe0-102">checked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="42fe0-102">checked (C# Reference)</span></span>

<span data-ttu-id="42fe0-103">Ключевое слово `checked` используется для явного включения проверки переполнения при выполнении арифметических операций и преобразований с данными целого типа.</span><span class="sxs-lookup"><span data-stu-id="42fe0-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="42fe0-104">По умолчанию выражение, содержащее только константные значения, вызывает ошибку компилятора в том случае, если результат его вычисления выходит за допустимые пределы значений конечного типа.</span><span class="sxs-lookup"><span data-stu-id="42fe0-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="42fe0-105">Если выражение содержит одно или несколько неконстантных значений, компилятор не выполняет проверку переполнения.</span><span class="sxs-lookup"><span data-stu-id="42fe0-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="42fe0-106">Вычисление выражения, присвоенного переменной `i2` в приведенном ниже примере, не вызывает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="42fe0-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="42fe0-107">По умолчанию эти неконстантные выражения также не проверяются на переполнение во время выполнения, и они не создают исключений переполнения.</span><span class="sxs-lookup"><span data-stu-id="42fe0-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="42fe0-108">В предыдущем примере в качестве суммы двух положительных целых чисел выводится значение -2 147 483 639.</span><span class="sxs-lookup"><span data-stu-id="42fe0-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="42fe0-109">Проверку переполнения можно включить посредством параметров компилятора, настройки среды или использования ключевого слова `checked`.</span><span class="sxs-lookup"><span data-stu-id="42fe0-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="42fe0-110">В следующих примерах демонстрируется использование выражения `checked` или блока `checked` для обнаружения переполнения, возникающего в результате предыдущего сложения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="42fe0-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="42fe0-111">В обоих примерах создается исключение переполнения.</span><span class="sxs-lookup"><span data-stu-id="42fe0-111">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="42fe0-112">Для запрета проверки переполнения можно использовать ключевое слово [unchecked](../../../csharp/language-reference/keywords/unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="42fe0-112">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="42fe0-113">Пример</span><span class="sxs-lookup"><span data-stu-id="42fe0-113">Example</span></span>

<span data-ttu-id="42fe0-114">В этом примере демонстрируется включение проверки переполнения во время выполнения посредством ключевого слова `checked`.</span><span class="sxs-lookup"><span data-stu-id="42fe0-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="42fe0-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="42fe0-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="42fe0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="42fe0-116">See also</span></span>

- [<span data-ttu-id="42fe0-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="42fe0-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="42fe0-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="42fe0-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="42fe0-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="42fe0-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="42fe0-120">Операторы checked и unchecked</span><span class="sxs-lookup"><span data-stu-id="42fe0-120">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
- [<span data-ttu-id="42fe0-121">unchecked</span><span class="sxs-lookup"><span data-stu-id="42fe0-121">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)
