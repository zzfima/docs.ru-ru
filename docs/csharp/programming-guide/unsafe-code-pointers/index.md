---
title: Руководство по программированию на C#. Небезопасный код и указатели
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 013af4e55c8fc396bbc92058d7fb454484f3263e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711835"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="cbfeb-102">Руководство по программированию на C#. Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="cbfeb-102">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="cbfeb-103">Для обеспечения типобезопасности и безопасности язык C# по умолчанию не поддерживает арифметику указателей.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="cbfeb-104">Но ключевое слово [unsafe](../../language-reference/keywords/unsafe.md) позволяет задать небезопасный контекст, в котором использование указателей возможно.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-104">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="cbfeb-105">Дополнительные сведения об указателях см. в разделе [Типы указателей (Руководство по программированию на C#)](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="cbfeb-105">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbfeb-106">В общеязыковой среде выполнения (CLR) небезопасный код называется непроверяемым.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="cbfeb-107">Небезопасный код в C# не обязательно опасен, просто его безопасность нельзя проверить в CLR.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="cbfeb-108">Поэтому CLR будет выполнять небезопасный код, только если он находится в полностью доверенной сборке.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="cbfeb-109">Если вы используете небезопасный код, вы сами несете ответственность за возможные риски безопасности и ошибки указателей.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="cbfeb-110">Общие сведения о небезопасном коде</span><span class="sxs-lookup"><span data-stu-id="cbfeb-110">Unsafe code overview</span></span>

<span data-ttu-id="cbfeb-111">Небезопасный код имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="cbfeb-111">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="cbfeb-112">Методы, типы и блоки кода можно определить как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-112">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="cbfeb-113">В некоторых случаях небезопасный код может увеличить скорость работы приложения, если не проверяются границы массивов.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="cbfeb-114">Небезопасный код необходим при вызове встроенных стандартных функций, требующих указателей.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-114">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="cbfeb-115">Использование небезопасного кода создает риски для стабильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="cbfeb-115">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="cbfeb-116">Код, содержащий небезопасные блоки, должен компилироваться с параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="cbfeb-116">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="cbfeb-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cbfeb-117">Related sections</span></span>

<span data-ttu-id="cbfeb-118">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="cbfeb-118">For more information, see:</span></span>

- [<span data-ttu-id="cbfeb-119">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="cbfeb-119">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="cbfeb-120">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="cbfeb-120">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="cbfeb-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="cbfeb-121">C# language specification</span></span>

<span data-ttu-id="cbfeb-122">Дополнительные сведения см. в разделе [Небезопасный код](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="cbfeb-122">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cbfeb-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbfeb-123">See also</span></span>

- [<span data-ttu-id="cbfeb-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cbfeb-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cbfeb-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="cbfeb-125">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
