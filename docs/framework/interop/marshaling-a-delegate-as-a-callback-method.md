---
title: Маршалинг делегата как метода обратного вызова
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e2289b3c12c7c83a39f1ad8d5a1365349ca6442
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151797"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="24353-102">Маршалинг делегата как метода обратного вызова</span><span class="sxs-lookup"><span data-stu-id="24353-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="24353-103">В этом примере показан способ передачи делегатов в неуправляемую функцию, ожидающую указатели на функции.</span><span class="sxs-lookup"><span data-stu-id="24353-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="24353-104">Делегат — это класс, который может содержать ссылку на метод. Делегат эквивалентен типобезопасному указателю на функцию или функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="24353-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>

> [!NOTE]
> <span data-ttu-id="24353-105">При использовании делегата в вызове функции общеязыковая среда выполнения защищает делегат от сборщика мусора в течение этого вызова.</span><span class="sxs-lookup"><span data-stu-id="24353-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="24353-106">Однако если неуправляемая функция сохраняет делегат для использования после завершения вызова, необходимо вручную запретить сбор мусора до того, как неуправляемая функция завершит обработку делегата.</span><span class="sxs-lookup"><span data-stu-id="24353-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="24353-107">Дополнительные сведения см. в разделах [Пример HandleRef](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) и [Пример GCHandle](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="24353-107">For more information, see the [HandleRef Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) and [GCHandle Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).</span></span>

<span data-ttu-id="24353-108">В примере обратного вызова используются следующие неуправляемые функции со своими первоначальными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="24353-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="24353-109">`TestCallBack` экспортируется из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="24353-109">`TestCallBack` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack(FPTR pf, int value);
    ```

- <span data-ttu-id="24353-110">`TestCallBack2` экспортируется из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="24353-110">`TestCallBack2` exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestCallBack2(FPTR2 pf2, char* value);
    ```

<span data-ttu-id="24353-111">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций.</span><span class="sxs-lookup"><span data-stu-id="24353-111">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>

<span data-ttu-id="24353-112">В этом примере класс `NativeMethods` содержит управляемые прототипы методов `TestCallBack` и `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="24353-112">In this sample, the `NativeMethods` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="24353-113">Оба метода передают делегат функции обратного вызова в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="24353-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="24353-114">Сигнатура делегата должна соответствовать сигнатуре метода, на который ссылается делегат.</span><span class="sxs-lookup"><span data-stu-id="24353-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="24353-115">Например, подписи делегатов для `FPtr` и `FPtr2` аналогичны методам `DoSomething` и `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="24353-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>

## <a name="declaring-prototypes"></a><span data-ttu-id="24353-116">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="24353-116">Declaring Prototypes</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
[!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
[!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]

## <a name="calling-functions"></a><span data-ttu-id="24353-117">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="24353-117">Calling Functions</span></span>
[!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
[!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
[!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]

## <a name="see-also"></a><span data-ttu-id="24353-118">См. также</span><span class="sxs-lookup"><span data-stu-id="24353-118">See also</span></span>

- <span data-ttu-id="24353-119">[Различные примеры маршалинга](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="24353-119">[Miscellaneous Marshaling Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))</span></span>
- [<span data-ttu-id="24353-120">Типы данных в вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="24353-120">Platform Invoke Data Types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="24353-121">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="24353-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
