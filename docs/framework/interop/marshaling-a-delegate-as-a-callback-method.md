---
title: "Маршалинг делегата как метода обратного вызова"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d9269261c6c0ce7573e0a8e298111971ae591c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="d5be0-102">Маршалинг делегата как метода обратного вызова</span><span class="sxs-lookup"><span data-stu-id="d5be0-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="d5be0-103">В этом примере показан способ передачи делегатов в неуправляемую функцию, ожидающую указатели на функции.</span><span class="sxs-lookup"><span data-stu-id="d5be0-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="d5be0-104">Делегат — это класс, который может содержать ссылку на метод. Делегат эквивалентен типобезопасному указателю на функцию или функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="d5be0-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5be0-105">При использовании делегата в вызове функции общеязыковая среда выполнения защищает делегат от сборщика мусора в течение этого вызова.</span><span class="sxs-lookup"><span data-stu-id="d5be0-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="d5be0-106">Однако если неуправляемая функция сохраняет делегат для использования после завершения вызова, необходимо вручную запретить сбор мусора до того, как неуправляемая функция завершит обработку делегата.</span><span class="sxs-lookup"><span data-stu-id="d5be0-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="d5be0-107">Дополнительные сведения см. в разделах [Пример HandleRef](http://msdn.microsoft.com/en-us/ab23b04e-1d53-4ec7-b27a-e892d9298959) и [Пример GCHandle](http://msdn.microsoft.com/en-us/6acce798-0385-4ded-a790-77da842c113f).</span><span class="sxs-lookup"><span data-stu-id="d5be0-107">For more information, see the [HandleRef Sample](http://msdn.microsoft.com/en-us/ab23b04e-1d53-4ec7-b27a-e892d9298959) and [GCHandle Sample](http://msdn.microsoft.com/en-us/6acce798-0385-4ded-a790-77da842c113f).</span></span>  
  
 <span data-ttu-id="d5be0-108">В примере обратного вызова используются следующие неуправляемые функции со своими первоначальными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="d5be0-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="d5be0-109">функция **TestCallBack**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="d5be0-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="d5be0-110">функция **TestCallBack2**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="d5be0-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="d5be0-111">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций.</span><span class="sxs-lookup"><span data-stu-id="d5be0-111">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="d5be0-112">В этом примере класс `LibWrap` содержит управляемые прототипы методов `TestCallBack` и `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="d5be0-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="d5be0-113">Оба метода передают делегат функции обратного вызова в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="d5be0-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="d5be0-114">Сигнатура делегата должна соответствовать сигнатуре метода, на который ссылается делегат.</span><span class="sxs-lookup"><span data-stu-id="d5be0-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="d5be0-115">Например, подписи делегатов для `FPtr` и `FPtr2` аналогичны методам `DoSomething` и `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="d5be0-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="d5be0-116">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="d5be0-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="d5be0-117">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="d5be0-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="d5be0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d5be0-118">See Also</span></span>  
 [<span data-ttu-id="d5be0-119">Различные примеры маршалинга</span><span class="sxs-lookup"><span data-stu-id="d5be0-119">Miscellaneous Marshaling Samples</span></span>](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)  
 [<span data-ttu-id="d5be0-120">Типы данных вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="d5be0-120">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="d5be0-121">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="d5be0-121">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
