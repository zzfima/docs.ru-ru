---
title: Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
ms.openlocfilehash: d746355dac1b99690a5a94c829bd35598c6c8be8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328868"
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="187b7-102">Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="187b7-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="187b7-103">В этом примере показывается, как использовать перегрузку оператора для создания класса комплексных чисел `Complex`, определяющего сложение комплексных чисел.</span><span class="sxs-lookup"><span data-stu-id="187b7-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="187b7-104">Программа выводит мнимую и реальную части чисел, а также результат сложения, используя переопределение метода `ToString`.</span><span class="sxs-lookup"><span data-stu-id="187b7-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="187b7-105">Пример</span><span class="sxs-lookup"><span data-stu-id="187b7-105">Example</span></span>  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="187b7-106">См. также</span><span class="sxs-lookup"><span data-stu-id="187b7-106">See Also</span></span>  
 [<span data-ttu-id="187b7-107">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="187b7-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="187b7-108">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="187b7-108">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="187b7-109">operator (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="187b7-109">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="187b7-110">Почему перегруженные операторы всегда являются статическими в C#?</span><span class="sxs-lookup"><span data-stu-id="187b7-110">Why are overloaded operators always static in C#?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
