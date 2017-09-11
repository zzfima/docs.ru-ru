---
title: "Практическое руководство. Реализация определенных пользователем преобразований между структурами (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
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
ms.openlocfilehash: cc8856bb3bf8943c1b6648f7d81447a3e59b9489
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="21fd8-102">Практическое руководство. Реализация определенных пользователем преобразований между структурами (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="21fd8-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="21fd8-103">В этом примере определяются две структуры (`RomanNumeral` и `BinaryNumeral`) и демонстрируются преобразования между ними.</span><span class="sxs-lookup"><span data-stu-id="21fd8-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21fd8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="21fd8-104">Example</span></span>  
 <span data-ttu-id="21fd8-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="21fd8-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="21fd8-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="21fd8-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="21fd8-107">В предыдущем примере инструкция:</span><span class="sxs-lookup"><span data-stu-id="21fd8-107">In the previous example, the statement:</span></span>  
  
     <span data-ttu-id="21fd8-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="21fd8-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span></span>  
  
     <span data-ttu-id="21fd8-109">выполняет преобразование из `RomanNumeral` в `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="21fd8-109">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="21fd8-110">Поскольку прямого преобразования из `RomanNumeral` в `BinaryNumeral` не существует, используется приведение для преобразования из `RomanNumeral` в `int` и еще одно приведение для преобразования из `int` в `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="21fd8-110">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="21fd8-111">Кроме того, инструкция</span><span class="sxs-lookup"><span data-stu-id="21fd8-111">Also the statement</span></span>  
  
     <span data-ttu-id="21fd8-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="21fd8-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span></span>  
  
     <span data-ttu-id="21fd8-113">выполняет преобразование из `BinaryNumeral` в `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="21fd8-113">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="21fd8-114">Поскольку `RomanNumeral` определяет неявное преобразование из `BinaryNumeral`, приведение не требуется.</span><span class="sxs-lookup"><span data-stu-id="21fd8-114">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fd8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="21fd8-115">See Also</span></span>  
 <span data-ttu-id="21fd8-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="21fd8-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="21fd8-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="21fd8-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="21fd8-118">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="21fd8-118">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

