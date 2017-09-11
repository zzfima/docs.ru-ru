---
title: "unchecked (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
dev_langs:
- CSharp
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
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
ms.openlocfilehash: 5878a2412e6c85da85b1a3b8c2a8255b51e67137
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="unchecked-c-reference"></a><span data-ttu-id="fcec7-102">unchecked (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fcec7-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="fcec7-103">Ключевое слово `unchecked` позволяет предотвратить проверку переполнения при выполнении арифметических операций и преобразований с данными целого типа.</span><span class="sxs-lookup"><span data-stu-id="fcec7-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="fcec7-104">В непроверенном контексте перегрузка не помечается, если результат выражения выходит за допустимые пределы значений конечного типа.</span><span class="sxs-lookup"><span data-stu-id="fcec7-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="fcec7-105">Например, в связи с тем, что вычисление в приведенном выше примере выполняется в блоке или выражении `unchecked`, тот факт, что результат слишком велик для целого числа, игнорируется, а `int1` присваивается значение -2,147,483,639.</span><span class="sxs-lookup"><span data-stu-id="fcec7-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 <span data-ttu-id="fcec7-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fcec7-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span></span>  
  
 <span data-ttu-id="fcec7-107">При удалении среды `unchecked` возникает ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="fcec7-107">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="fcec7-108">Во время компиляции может быть обнаружено переполнение, поскольку все члены данного выражения являются константами.</span><span class="sxs-lookup"><span data-stu-id="fcec7-108">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="fcec7-109">Выражения, содержащие члены, которые не являются константами, по умолчанию не проверяются ни во время компиляции, ни во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fcec7-109">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="fcec7-110">Дополнительные сведения о включении проверяемой среды см. в разделе [checked](../../../csharp/language-reference/keywords/checked.md).</span><span class="sxs-lookup"><span data-stu-id="fcec7-110">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="fcec7-111">Поскольку проверка на переполнение занимает определенное время, в ситуациях, где нет опасности переполнения, можно повысить производительность, выбрав непроверяемый код.</span><span class="sxs-lookup"><span data-stu-id="fcec7-111">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="fcec7-112">Если же переполнение вероятно, следует использовать проверяемую среду.</span><span class="sxs-lookup"><span data-stu-id="fcec7-112">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcec7-113">Пример</span><span class="sxs-lookup"><span data-stu-id="fcec7-113">Example</span></span>  
 <span data-ttu-id="fcec7-114">В этом примере демонстрируется применение ключевого слова `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="fcec7-114">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 <span data-ttu-id="fcec7-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fcec7-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fcec7-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fcec7-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fcec7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fcec7-117">See Also</span></span>  
 <span data-ttu-id="fcec7-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcec7-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fcec7-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcec7-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fcec7-120">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcec7-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fcec7-121">[Операторы checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="fcec7-121">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="fcec7-122">checked</span><span class="sxs-lookup"><span data-stu-id="fcec7-122">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)

