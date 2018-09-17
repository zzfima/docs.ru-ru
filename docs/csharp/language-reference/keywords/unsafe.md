---
title: unsafe (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: b4615021a4fc3391ac0ae703b6c97301b44aa60e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45596549"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="ebaba-102">unsafe (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ebaba-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="ebaba-103">Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для выполнения любых операций с применением указателей.</span><span class="sxs-lookup"><span data-stu-id="ebaba-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="ebaba-104">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="ebaba-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="ebaba-105">В объявлении типа или члена типа можно использовать модификатор `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="ebaba-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="ebaba-106">Все текстовое пространство типа или члена типа считается небезопасным контекстом.</span><span class="sxs-lookup"><span data-stu-id="ebaba-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="ebaba-107">Например, следующий метод объявлен с модификатором `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="ebaba-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```csharp  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="ebaba-108">Область небезопасного контекста простирается от списка параметров до конца метода, поэтому в списке параметров можно также использовать указатели:</span><span class="sxs-lookup"><span data-stu-id="ebaba-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="ebaba-109">Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок.</span><span class="sxs-lookup"><span data-stu-id="ebaba-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="ebaba-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="ebaba-110">For example:</span></span>  
  
```csharp  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="ebaba-111">Для компиляции небезопасного кода необходимо задать параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ebaba-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="ebaba-112">Небезопасный код не проверяется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ebaba-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebaba-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ebaba-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ebaba-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ebaba-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ebaba-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ebaba-115">See Also</span></span>

- [<span data-ttu-id="ebaba-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ebaba-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ebaba-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ebaba-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ebaba-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ebaba-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ebaba-119">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="ebaba-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="ebaba-120">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="ebaba-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="ebaba-121">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="ebaba-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
