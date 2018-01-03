---
title: "Функции обратного вызова"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4f39160e817ce04c5c15fb8299852a052d36c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions"></a><span data-ttu-id="61cc0-102">Функции обратного вызова</span><span class="sxs-lookup"><span data-stu-id="61cc0-102">Callback Functions</span></span>
<span data-ttu-id="61cc0-103">Функция обратного вызова — это программный код в управляемом приложении, который помогает неуправляемой функции DLL выполнить задачу.</span><span class="sxs-lookup"><span data-stu-id="61cc0-103">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="61cc0-104">Вызовы функции обратного вызова косвенно, через функцию DLL, передаются из управляемого приложения и возвращаются в управляемую реализацию.</span><span class="sxs-lookup"><span data-stu-id="61cc0-104">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="61cc0-105">Лишь некоторые из многих функций DLL, вызываемых в вызове неуправляемого кода, требуют для своего выполнения наличия в управляемом коде функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="61cc0-105">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="61cc0-106">Для вызова большинства функций DLL из управляемого кода нужно создать управляемое определение функции и затем выполнить сам вызов.</span><span class="sxs-lookup"><span data-stu-id="61cc0-106">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="61cc0-107">Этот процесс достаточно прост.</span><span class="sxs-lookup"><span data-stu-id="61cc0-107">The process is straightforward.</span></span>  
  
 <span data-ttu-id="61cc0-108">Применение функции DLL, требующей наличия функции обратного вызова, предполагает выполнение некоторых дополнительных шагов.</span><span class="sxs-lookup"><span data-stu-id="61cc0-108">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="61cc0-109">Во-первых, необходимо определить, требуется ли для функции обратный вызов. Это можно выяснить в документации по функции.</span><span class="sxs-lookup"><span data-stu-id="61cc0-109">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="61cc0-110">Далее нужно создать функцию обратного вызова в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="61cc0-110">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="61cc0-111">И, наконец, вы вызываете функцию DLL, передавая указатель на функцию обратного вызова в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="61cc0-111">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span> <span data-ttu-id="61cc0-112">Перечисленные действия показаны на приведенной ниже иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="61cc0-112">The following illustration summarizes these steps.</span></span>  
  
 <span data-ttu-id="61cc0-113">![Обратный вызов неуправляемого кода](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")</span><span class="sxs-lookup"><span data-stu-id="61cc0-113">![Platform invoke callback](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")</span></span>  
<span data-ttu-id="61cc0-114">Функция обратного вызова и реализация</span><span class="sxs-lookup"><span data-stu-id="61cc0-114">Callback function and implementation</span></span>  
  
 <span data-ttu-id="61cc0-115">Функции обратного вызова — идеальное средство для многократного выполнения некоторой задачи.</span><span class="sxs-lookup"><span data-stu-id="61cc0-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="61cc0-116">Другая область их применения — с функциями перечисления интерфейса Win32 API, такими как **EnumFontFamilies**, **EnumPrinters** и **EnumWindows**.</span><span class="sxs-lookup"><span data-stu-id="61cc0-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Win32 API.</span></span> <span data-ttu-id="61cc0-117">Функция **EnumWindows** выполняет перечисление всех существующих на компьютере окон, используя функцию обратного вызова, чтобы выполнить задачу для каждого окна.</span><span class="sxs-lookup"><span data-stu-id="61cc0-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="61cc0-118">Инструкции и пример см. в разделе [Практическое руководство. Реализация функций обратного вызова](../../../docs/framework/interop/how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="61cc0-118">For instructions and an example, see [How to: Implement Callback Functions](../../../docs/framework/interop/how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cc0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="61cc0-119">See Also</span></span>  
 [<span data-ttu-id="61cc0-120">Практическое руководство. Реализация функций обратного вызова</span><span class="sxs-lookup"><span data-stu-id="61cc0-120">How to: Implement Callback Functions</span></span>](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [<span data-ttu-id="61cc0-121">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="61cc0-121">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
