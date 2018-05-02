---
title: Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)
ms.date: 04/20/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6e87a2ec2c04812ac9b998c4c6d9a18d1b097342
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="0c31f-102">Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0c31f-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>

<span data-ttu-id="0c31f-103">В следующем примере указатели используются для копирования байт из одного массива в другой.</span><span class="sxs-lookup"><span data-stu-id="0c31f-103">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="0c31f-104">В этом примере применяется ключевое слово [unsafe](../../language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`.</span><span class="sxs-lookup"><span data-stu-id="0c31f-104">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="0c31f-105">Оператор [fixed](../../language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массивов.</span><span class="sxs-lookup"><span data-stu-id="0c31f-105">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="0c31f-106">Оператор `fixed` *закрепляет* расположение исходного и конечного массивов в памяти, чтобы они не перемещались при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="0c31f-106">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="0c31f-107">Закрепление этих блоков памяти отменяется, когда завершается обработка блока `fixed`.</span><span class="sxs-lookup"><span data-stu-id="0c31f-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="0c31f-108">Поскольку метод `Copy` в этом примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0c31f-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="0c31f-109">В этом примере доступ к элементам обоих массивов выполняется с помощью индексов, а не второго неуправляемого указателя.</span><span class="sxs-lookup"><span data-stu-id="0c31f-109">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="0c31f-110">Объявление указателей `pSource` и `pTarget` закрепляет массивы.</span><span class="sxs-lookup"><span data-stu-id="0c31f-110">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="0c31f-111">Эта возможность доступна начиная с C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="0c31f-111">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="0c31f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0c31f-112">Example</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="0c31f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0c31f-113">See Also</span></span>
 [<span data-ttu-id="0c31f-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0c31f-114">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="0c31f-115">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="0c31f-115">Unsafe Code and Pointers</span></span>](index.md)  
 [<span data-ttu-id="0c31f-116">-unsafe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="0c31f-116">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)  
 [<span data-ttu-id="0c31f-117">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="0c31f-117">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
