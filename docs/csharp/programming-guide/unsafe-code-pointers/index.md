---
title: "Небезопасный код и указатели (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75e11b34f0749270650e0e5b5a2a191a1b9e9f9a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="c2918-102">Небезопасный код и указатели (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="c2918-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="c2918-103">Для обеспечения типобезопасности и безопасности язык C# по умолчанию не поддерживает арифметику указателей.</span><span class="sxs-lookup"><span data-stu-id="c2918-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="c2918-104">Но ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md) позволяет задать небезопасный контекст, в котором использование указателей возможно.</span><span class="sxs-lookup"><span data-stu-id="c2918-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="c2918-105">Дополнительные сведения об указателях см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="c2918-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2918-106">В общеязыковой среде выполнения (CLR) небезопасный код называется непроверяемым.</span><span class="sxs-lookup"><span data-stu-id="c2918-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="c2918-107">Небезопасный код в C# не обязательно опасен, просто его безопасность нельзя проверить в CLR.</span><span class="sxs-lookup"><span data-stu-id="c2918-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="c2918-108">Поэтому CLR будет выполнять небезопасный код, только если он находится в полностью доверенной сборке.</span><span class="sxs-lookup"><span data-stu-id="c2918-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="c2918-109">Если вы используете небезопасный код, вы сами несете ответственность за возможные риски безопасности и ошибки указателей.</span><span class="sxs-lookup"><span data-stu-id="c2918-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="c2918-110">Общие сведения о небезопасном коде</span><span class="sxs-lookup"><span data-stu-id="c2918-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="c2918-111">Небезопасный код имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="c2918-111">Unsafe code has the following properties:</span></span>  
  
-   <span data-ttu-id="c2918-112">Методы, типы и блоки кода можно определить как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="c2918-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
-   <span data-ttu-id="c2918-113">В некоторых случаях небезопасный код может увеличить скорость работы приложения, если не проверяются границы массивов.</span><span class="sxs-lookup"><span data-stu-id="c2918-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
-   <span data-ttu-id="c2918-114">Небезопасный код необходим при вызове встроенных стандартных функций, требующих указателей.</span><span class="sxs-lookup"><span data-stu-id="c2918-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
-   <span data-ttu-id="c2918-115">Использование небезопасного кода создает риски для стабильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="c2918-115">Using unsafe code introduces security and stability risks.</span></span>  
  
-   <span data-ttu-id="c2918-116">Чтобы скомпилировать небезопасный код на C#, приложение нужно компилировать с помощью [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c2918-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c2918-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c2918-117">Related Sections</span></span>  
 <span data-ttu-id="c2918-118">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="c2918-118">For more information, see:</span></span>  
  
-   [<span data-ttu-id="c2918-119">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="c2918-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [<span data-ttu-id="c2918-120">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="c2918-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [<span data-ttu-id="c2918-121">Практическое руководство. Использование указателей для копирования массива байтов</span><span class="sxs-lookup"><span data-stu-id="c2918-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [<span data-ttu-id="c2918-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="c2918-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="c2918-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c2918-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2918-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c2918-124">See Also</span></span>  
 [<span data-ttu-id="c2918-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c2918-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

