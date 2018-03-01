---
title: "unchecked (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c05e7cb742d8e8f5a7804656a5ec13548d0498b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="67a56-102">unchecked (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="67a56-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="67a56-103">Ключевое слово `unchecked` позволяет предотвратить проверку переполнения при выполнении арифметических операций и преобразований с данными целого типа.</span><span class="sxs-lookup"><span data-stu-id="67a56-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="67a56-104">В непроверенном контексте перегрузка не помечается, если результат выражения выходит за допустимые пределы значений конечного типа.</span><span class="sxs-lookup"><span data-stu-id="67a56-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="67a56-105">Например, в связи с тем, что вычисление в приведенном выше примере выполняется в блоке или выражении `unchecked`, тот факт, что результат слишком велик для целого числа, игнорируется, а `int1` присваивается значение -2,147,483,639.</span><span class="sxs-lookup"><span data-stu-id="67a56-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 <span data-ttu-id="67a56-106">При удалении среды `unchecked` возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="67a56-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="67a56-107">Во время компиляции может быть обнаружено переполнение, поскольку все члены данного выражения являются константами.</span><span class="sxs-lookup"><span data-stu-id="67a56-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="67a56-108">Выражения, содержащие члены, которые не являются константами, по умолчанию не проверяются ни во время компиляции, ни во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="67a56-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="67a56-109">Дополнительные сведения о включении проверяемой среды см. в разделе [checked](../../../csharp/language-reference/keywords/checked.md).</span><span class="sxs-lookup"><span data-stu-id="67a56-109">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="67a56-110">Поскольку проверка на переполнение занимает определенное время, в ситуациях, где нет опасности переполнения, можно повысить производительность, выбрав непроверяемый код.</span><span class="sxs-lookup"><span data-stu-id="67a56-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="67a56-111">Если же переполнение вероятно, следует использовать проверяемую среду.</span><span class="sxs-lookup"><span data-stu-id="67a56-111">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a56-112">Пример</span><span class="sxs-lookup"><span data-stu-id="67a56-112">Example</span></span>  
 <span data-ttu-id="67a56-113">В этом примере демонстрируется применение ключевого слова `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="67a56-113">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="67a56-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="67a56-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67a56-115">См. также</span><span class="sxs-lookup"><span data-stu-id="67a56-115">See Also</span></span>  
 [<span data-ttu-id="67a56-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="67a56-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="67a56-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="67a56-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="67a56-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="67a56-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="67a56-119">Операторы checked и unchecked</span><span class="sxs-lookup"><span data-stu-id="67a56-119">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="67a56-120">checked</span><span class="sxs-lookup"><span data-stu-id="67a56-120">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)
