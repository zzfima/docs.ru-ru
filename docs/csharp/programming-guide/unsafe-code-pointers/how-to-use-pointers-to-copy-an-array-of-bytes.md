---
title: "Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
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
ms.openlocfilehash: 808a74f75e4dcbcec47735d98063138e2c7456e5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="d604e-102">Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d604e-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="d604e-103">В следующем примере указатели используются для копирования байт из одного массива в другой.</span><span class="sxs-lookup"><span data-stu-id="d604e-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="d604e-104">В этом примере применяется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`.</span><span class="sxs-lookup"><span data-stu-id="d604e-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="d604e-105">Оператор [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массивов.</span><span class="sxs-lookup"><span data-stu-id="d604e-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="d604e-106">Это *закрепляет* расположение исходного и конечного массивов в памяти, чтобы они не перемещались при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="d604e-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="d604e-107">Закрепление этих блоков памяти отменяется, когда завершается обработка блока `fixed`.</span><span class="sxs-lookup"><span data-stu-id="d604e-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="d604e-108">Поскольку метод `Copy` в этом примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора **/unsafe**.</span><span class="sxs-lookup"><span data-stu-id="d604e-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="d604e-109">Чтобы задать параметр в Visual Studio, щелкните правой кнопкой мыши имя проекта, затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d604e-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="d604e-110">На вкладке **Сборка** выберите **Разрешить небезопасный код**.</span><span class="sxs-lookup"><span data-stu-id="d604e-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d604e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="d604e-111">Example</span></span>  
 <span data-ttu-id="d604e-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d604e-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span></span>  
  
 <span data-ttu-id="d604e-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d604e-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d604e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d604e-114">See Also</span></span>  
 <span data-ttu-id="d604e-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d604e-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d604e-116">[Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="d604e-116">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="d604e-117">[/unsafe (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="d604e-117">[/unsafe (C# Compiler Options)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span></span>  
 [<span data-ttu-id="d604e-118">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="d604e-118">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

