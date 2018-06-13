---
title: Идентификация функций в библиотеках DLL
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc160678817266dc649f60dc3f2cc77044c05691
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388623"
---
# <a name="identifying-functions-in-dlls"></a><span data-ttu-id="69af1-102">Идентификация функций в библиотеках DLL</span><span class="sxs-lookup"><span data-stu-id="69af1-102">Identifying Functions in DLLs</span></span>
<span data-ttu-id="69af1-103">Идентификатор функции DLL состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="69af1-103">The identity of a DLL function consists of the following elements:</span></span>  
  
-   <span data-ttu-id="69af1-104">Имя функции или порядковый номер</span><span class="sxs-lookup"><span data-stu-id="69af1-104">Function name or ordinal</span></span>  
  
-   <span data-ttu-id="69af1-105">Имя файла DLL, в котором находится реализация</span><span class="sxs-lookup"><span data-stu-id="69af1-105">Name of the DLL file in which the implementation can be found</span></span>  
  
 <span data-ttu-id="69af1-106">Например, при указании функции **MessageBox** в библиотеке User32.dll определяется функция (**MessageBox**) и ее расположение (User32.dll, User32 или user32).</span><span class="sxs-lookup"><span data-stu-id="69af1-106">For example, specifying the **MessageBox** function in the User32.dll identifies the function (**MessageBox**) and its location (User32.dll, User32, or user32).</span></span> <span data-ttu-id="69af1-107">Прикладной программный интерфейс приложений Microsoft Windows (API Win32) может содержать две версии для каждой функции, обрабатывающей символы и строки: версию ANSI для однобайтовых символов и версию Юникода для двухбайтовых символов.</span><span class="sxs-lookup"><span data-stu-id="69af1-107">The Microsoft Windows application programming interface (Win32 API) can contain two versions of each function that handles characters and strings: a 1-byte character ANSI version and a 2-byte character Unicode version.</span></span> <span data-ttu-id="69af1-108">Если кодировка не указана, она определяется полем <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> (по умолчанию ANSI).</span><span class="sxs-lookup"><span data-stu-id="69af1-108">When unspecified, the character set, represented by the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field, defaults to ANSI.</span></span> <span data-ttu-id="69af1-109">Некоторые функции могут иметь более двух версий.</span><span class="sxs-lookup"><span data-stu-id="69af1-109">Some functions can have more than two versions.</span></span>  
  
 <span data-ttu-id="69af1-110">**MessageBoxA** — это точка входа ANSI для функции **MessageBox**; **MessageBoxW** — версия для Юникода.</span><span class="sxs-lookup"><span data-stu-id="69af1-110">**MessageBoxA** is the ANSI entry point for the **MessageBox** function; **MessageBoxW** is the Unicode version.</span></span> <span data-ttu-id="69af1-111">Чтобы получить список имен функций в конкретной библиотеке DLL, например user32.dll, можно воспользоваться различными средствами командной строки.</span><span class="sxs-lookup"><span data-stu-id="69af1-111">You can list function names for a specific DLL, such as user32.dll, by running a variety of command-line tools.</span></span> <span data-ttu-id="69af1-112">Например, для получения имен функций можно воспользоваться `dumpbin /exports user32.dll` или `link /dump /exports user32.dll`.</span><span class="sxs-lookup"><span data-stu-id="69af1-112">For example, you can use `dumpbin /exports user32.dll` or `link /dump /exports user32.dll` to obtain function names.</span></span>  
  
 <span data-ttu-id="69af1-113">Неуправляемую функцию в коде можно переименовать, при условии что новое имя функции соответствует исходной точке входа в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="69af1-113">You can rename an unmanaged function to whatever you like within your code as long as you map the new name to the original entry point in the DLL.</span></span> <span data-ttu-id="69af1-114">Инструкции по переименованию неуправляемой функции DLL в управляемом исходном коде см. в разделе [Указание точки входа](../../../docs/framework/interop/specifying-an-entry-point.md).</span><span class="sxs-lookup"><span data-stu-id="69af1-114">For instructions on renaming an unmanaged DLL function in managed source code, see the [Specifying an Entry Point](../../../docs/framework/interop/specifying-an-entry-point.md).</span></span>  
  
 <span data-ttu-id="69af1-115">Вызов неуправляемого кода позволяет управлять значительной частью операционной системы с помощью вызова функций в API Win32 и других библиотеках DLL.</span><span class="sxs-lookup"><span data-stu-id="69af1-115">Platform invoke enables you to control a significant portion of the operating system by calling functions in the Win32 API and other DLLs.</span></span> <span data-ttu-id="69af1-116">Наряду с API Win32 существует несколько других API-интерфейсов и библиотек DLL, для которых доступен вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="69af1-116">In addition to the Win32 API, there are numerous other APIs and DLLs available to you through platform invoke.</span></span>  
  
 <span data-ttu-id="69af1-117">В следующей таблице описаны несколько распространенных библиотек DLL в API Win32.</span><span class="sxs-lookup"><span data-stu-id="69af1-117">The following table describes several commonly used DLLs in the Win32 API.</span></span>  
  
|<span data-ttu-id="69af1-118">DLL</span><span class="sxs-lookup"><span data-stu-id="69af1-118">DLL</span></span>|<span data-ttu-id="69af1-119">Описание содержимого</span><span class="sxs-lookup"><span data-stu-id="69af1-119">Description of Contents</span></span>|  
|---------|-----------------------------|  
|<span data-ttu-id="69af1-120">GDI32.dll</span><span class="sxs-lookup"><span data-stu-id="69af1-120">GDI32.dll</span></span>|<span data-ttu-id="69af1-121">Функции интерфейса графических устройств (GDI) для вывода информации на устройство, например функции для рисования и управления шрифтами.</span><span class="sxs-lookup"><span data-stu-id="69af1-121">Graphics Device Interface (GDI) functions for device output, such as those for drawing and font management.</span></span>|  
|<span data-ttu-id="69af1-122">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="69af1-122">Kernel32.dll</span></span>|<span data-ttu-id="69af1-123">Низкоуровневые функции операционной системы для управления памятью и обработки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="69af1-123">Low-level operating system functions for memory management and resource handling.</span></span>|  
|<span data-ttu-id="69af1-124">User32.dll</span><span class="sxs-lookup"><span data-stu-id="69af1-124">User32.dll</span></span>|<span data-ttu-id="69af1-125">Функции управления Windows для обработки сообщений, таймеров, меню и обмена данными.</span><span class="sxs-lookup"><span data-stu-id="69af1-125">Windows management functions for message handling, timers, menus, and communications.</span></span>|  
  
 <span data-ttu-id="69af1-126">Полную документацию по API Win32 см. в разделе "Пакет SDK платформы".</span><span class="sxs-lookup"><span data-stu-id="69af1-126">For complete documentation on the Win32 API, see the Platform SDK.</span></span> <span data-ttu-id="69af1-127">Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="69af1-127">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69af1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="69af1-128">See Also</span></span>  
 [<span data-ttu-id="69af1-129">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="69af1-129">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="69af1-130">Задание точки входа</span><span class="sxs-lookup"><span data-stu-id="69af1-130">Specifying an Entry Point</span></span>](../../../docs/framework/interop/specifying-an-entry-point.md)  
 [<span data-ttu-id="69af1-131">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="69af1-131">Creating a Class to Hold DLL Functions</span></span>](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)  
 [<span data-ttu-id="69af1-132">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="69af1-132">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="69af1-133">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="69af1-133">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
