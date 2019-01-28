---
title: Как выполнить Руководство по программированию на C#. Реализация определенных пользователем преобразований между структурами
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 4b38271c1aaf582c8c58b7198765b679cdfe4881
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499568"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="9405d-102">Как выполнить Руководство по программированию на C#. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="9405d-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="9405d-103">В этом примере определяются две структуры (`RomanNumeral` и `BinaryNumeral`) и демонстрируются преобразования между ними.</span><span class="sxs-lookup"><span data-stu-id="9405d-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9405d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9405d-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9405d-105">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="9405d-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="9405d-106">В предыдущем примере инструкция:</span><span class="sxs-lookup"><span data-stu-id="9405d-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="9405d-107">выполняет преобразование из `RomanNumeral` в `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="9405d-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="9405d-108">Поскольку прямого преобразования из `RomanNumeral` в `BinaryNumeral` не существует, используется приведение для преобразования из `RomanNumeral` в `int` и еще одно приведение для преобразования из `int` в `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="9405d-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="9405d-109">Кроме того, инструкция</span><span class="sxs-lookup"><span data-stu-id="9405d-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="9405d-110">выполняет преобразование из `BinaryNumeral` в `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="9405d-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="9405d-111">Поскольку `RomanNumeral` определяет неявное преобразование из `BinaryNumeral`, приведение не требуется.</span><span class="sxs-lookup"><span data-stu-id="9405d-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9405d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9405d-112">See also</span></span>

- [<span data-ttu-id="9405d-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9405d-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="9405d-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9405d-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9405d-115">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="9405d-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
