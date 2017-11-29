---
title: "Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="a33e2-102">Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a33e2-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="a33e2-103">В следующем примере указатели используются для копирования байт из одного массива в другой.</span><span class="sxs-lookup"><span data-stu-id="a33e2-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="a33e2-104">В этом примере применяется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`.</span><span class="sxs-lookup"><span data-stu-id="a33e2-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="a33e2-105">Оператор [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массивов.</span><span class="sxs-lookup"><span data-stu-id="a33e2-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="a33e2-106">Это *закрепляет* расположение исходного и конечного массивов в памяти, чтобы они не перемещались при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="a33e2-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="a33e2-107">Закрепление этих блоков памяти отменяется, когда завершается обработка блока `fixed`.</span><span class="sxs-lookup"><span data-stu-id="a33e2-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="a33e2-108">Поскольку метод `Copy` в этом примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора **/unsafe**.</span><span class="sxs-lookup"><span data-stu-id="a33e2-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="a33e2-109">Чтобы задать параметр в Visual Studio, щелкните правой кнопкой мыши имя проекта, затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a33e2-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="a33e2-110">На вкладке **Сборка** выберите **Разрешить небезопасный код**.</span><span class="sxs-lookup"><span data-stu-id="a33e2-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33e2-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a33e2-111">Example</span></span>  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a33e2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a33e2-112">See Also</span></span>  
 [<span data-ttu-id="a33e2-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a33e2-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a33e2-114">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="a33e2-114">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="a33e2-115">/unsafe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a33e2-115">/unsafe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [<span data-ttu-id="a33e2-116">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="a33e2-116">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
