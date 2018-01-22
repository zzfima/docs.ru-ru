---
title: "Использование неуправляемых функций DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd1e5f4fc03da2310022efdeb4530440b5e07f3d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="aedf4-102">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="aedf4-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="aedf4-103">Вызов неуправляемого кода — это служба, позволяющая управляемому коду вызывать неуправляемые функции, реализованные в библиотеках динамической компоновки (DLL), например функции библиотек Win32 API.</span><span class="sxs-lookup"><span data-stu-id="aedf4-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Win32 API.</span></span> <span data-ttu-id="aedf4-104">Он обнаруживает и вызывает экспортированную функцию и при необходимости маршалирует ее аргументы (целые числа, строки, массивы, структуры и так далее) через границы взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="aedf4-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span> <span data-ttu-id="aedf4-105">Дополнительные сведения об этой службе см. в разделе [Подробный обзор вызова неуправляемого кода](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span><span class="sxs-lookup"><span data-stu-id="aedf4-105">For more information about this service, see [A Closer Look at Platform Invoke](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span></span>  
  
 <span data-ttu-id="aedf4-106">В этом разделе представлено несколько задач, связанных с использованием неуправляемых функций DLL.</span><span class="sxs-lookup"><span data-stu-id="aedf4-106">This section introduces several tasks associated with consuming unmanaged DLL functions.</span></span> <span data-ttu-id="aedf4-107">Кроме того, раздел содержит общие сведения и ссылки на дополнительную информацию и примеры.</span><span class="sxs-lookup"><span data-stu-id="aedf4-107">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="aedf4-108">Использование экспортированных функций DLL</span><span class="sxs-lookup"><span data-stu-id="aedf4-108">To consume exported DLL functions</span></span>  
  
1.  <span data-ttu-id="aedf4-109">[Идентификация функций в библиотеках DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="aedf4-109">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="aedf4-110">Как минимум, необходимо указать имя функции и имя библиотеки DLL, содержащей ее.</span><span class="sxs-lookup"><span data-stu-id="aedf4-110">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2.  <span data-ttu-id="aedf4-111">[Создание класса, содержащего функции DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="aedf4-111">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="aedf4-112">Можно использовать существующий класс, создать отдельный класс для каждой неуправляемой функции или создать один класс, содержащий набор связанных неуправляемых функций.</span><span class="sxs-lookup"><span data-stu-id="aedf4-112">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3.  <span data-ttu-id="aedf4-113">[Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="aedf4-113">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="aedf4-114">[Visual Basic] Используйте оператор **Declare** с ключевыми словами **Function** и **Lib**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-114">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="aedf4-115">В редких случаях можно использовать атрибут **DllImportAttribute** с ключевыми словами **Shared Function**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-115">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="aedf4-116">Такие случаи рассматриваются далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="aedf4-116">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="aedf4-117">[C#] Используйте атрибут **DllImportAttribute** для идентификации библиотеки DLL и функции.</span><span class="sxs-lookup"><span data-stu-id="aedf4-117">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="aedf4-118">Пометьте метод модификаторами **static** и **extern**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-118">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="aedf4-119">[C++] Используйте атрибут **DllImportAttribute** для идентификации библиотеки DLL и функции.</span><span class="sxs-lookup"><span data-stu-id="aedf4-119">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="aedf4-120">Пометьте метод или функцию оболочки модификатором **extern "C"**.</span><span class="sxs-lookup"><span data-stu-id="aedf4-120">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4.  <span data-ttu-id="aedf4-121">[Вызов функции DLL](../../../docs/framework/interop/calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="aedf4-121">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="aedf4-122">Вызовите метод управляемого класса так же, как и любой другой управляемый метод.</span><span class="sxs-lookup"><span data-stu-id="aedf4-122">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="aedf4-123">[Передача структур](../../../docs/framework/interop/passing-structures.md) и [реализация функций обратного вызова](../../../docs/framework/interop/callback-functions.md) представляют собой особые случаи.</span><span class="sxs-lookup"><span data-stu-id="aedf4-123">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="aedf4-124">Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="aedf4-124">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="aedf4-125">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="aedf4-125">A closer look at platform invoke</span></span>  
 <span data-ttu-id="aedf4-126">Вызов неуправляемого кода использует метаданные для нахождения экспортированных функций и маршалинга их аргументов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="aedf4-126">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="aedf4-127">Данный процесс показан на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="aedf4-127">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="aedf4-128">![Платформозависимый вызов](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span><span class="sxs-lookup"><span data-stu-id="aedf4-128">![Platform invoke](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span></span>  
<span data-ttu-id="aedf4-129">Вызов неуправляемой функции DLL с помощью вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="aedf4-129">A platform invoke call to an unmanaged DLL function</span></span>  
  
 <span data-ttu-id="aedf4-130">Когда неуправляемый код вызывает неуправляемую функцию, то он выполняет следующую последовательность действий:</span><span class="sxs-lookup"><span data-stu-id="aedf4-130">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1.  <span data-ttu-id="aedf4-131">Определяет библиотеку DLL, содержащую функцию.</span><span class="sxs-lookup"><span data-stu-id="aedf4-131">Locates the DLL containing the function.</span></span>  
  
2.  <span data-ttu-id="aedf4-132">Загружает библиотеку DLL в память.</span><span class="sxs-lookup"><span data-stu-id="aedf4-132">Loads the DLL into memory.</span></span>  
  
3.  <span data-ttu-id="aedf4-133">Находит адрес функции в памяти и помещает ее аргументы в стек, выполнив по необходимости маршалинг данных.</span><span class="sxs-lookup"><span data-stu-id="aedf4-133">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aedf4-134">Поиск и загрузка библиотеки DLL, а также определение адреса функции в памяти выполняются только при первом вызове функции.</span><span class="sxs-lookup"><span data-stu-id="aedf4-134">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4.  <span data-ttu-id="aedf4-135">Передает управление неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="aedf4-135">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="aedf4-136">Вызов неуправляемого кода вызывает исключения, создаваемые неуправляемой функцией для управляемого вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="aedf4-136">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedf4-137">См. также</span><span class="sxs-lookup"><span data-stu-id="aedf4-137">See Also</span></span>  
 [<span data-ttu-id="aedf4-138">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="aedf4-138">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="aedf4-139">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="aedf4-139">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="aedf4-140">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="aedf4-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="aedf4-141">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="aedf4-141">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
