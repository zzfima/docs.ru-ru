---
title: "Практическое руководство. Объявление констант в C#"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ff12d0b6882289da9ed924f1c7de00edc5dc1e2e
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="0a12c-102">Практическое руководство. Объявление констант в C#</span><span class="sxs-lookup"><span data-stu-id="0a12c-102">How to: Define Constants in C#</span></span>
<span data-ttu-id="0a12c-103">Константы — это поля, значения которых устанавливаются во время компиляции и не изменяются.</span><span class="sxs-lookup"><span data-stu-id="0a12c-103">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="0a12c-104">С помощью констант можно присвоить особым значениям значащие имена вместо числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="0a12c-104">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a12c-105">В C# с помощью директивы препроцессора [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) нельзя определять константы так, как это было реализовано в C и C++.</span><span class="sxs-lookup"><span data-stu-id="0a12c-105">In C# the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="0a12c-106">Чтобы определить значения константы целочисленного типа (`int`, `byte` и т. д.), используйте перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="0a12c-106">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="0a12c-107">Дополнительные сведения см. в разделе [Перечисление](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="0a12c-107">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="0a12c-108">Чтобы определить нецелочисленные константы, можно сгруппировать их в статический класс с именем `Constants`.</span><span class="sxs-lookup"><span data-stu-id="0a12c-108">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="0a12c-109">В этом случае перед любыми ссылками на константы будет необходимо указывать имя класса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0a12c-109">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a12c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0a12c-110">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 <span data-ttu-id="0a12c-111">Используя квалификатор имени класса, вы гарантируете, что вы сами и другие разработчики будете понимать, что имеете дело с константой, которую нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="0a12c-111">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a12c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0a12c-112">See Also</span></span>  
 [<span data-ttu-id="0a12c-113">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="0a12c-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
