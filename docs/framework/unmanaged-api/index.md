---
title: Справочник по неуправляемым API
ms.date: 11/06/2017
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
ms.openlocfilehash: f7dd78b889129998dee31a22f5dd23325613b8ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092015"
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="6dbf2-102">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="6dbf2-102">Unmanaged API Reference</span></span>
<span data-ttu-id="6dbf2-103">В данном разделе содержатся сведения о неуправляемых API, которые могут использоваться приложениями, связанными с управляемым кодом, например хост-приложениями среды выполнения, компиляторами, дизассемблерами, средствами запутывания, отладчиками и профилировщиками.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6dbf2-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6dbf2-104">In This Section</span></span>  
 [<span data-ttu-id="6dbf2-105">Общие типы данных</span><span class="sxs-lookup"><span data-stu-id="6dbf2-105">Common Data Types</span></span>](common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="6dbf2-106">Содержит список используемых общих типы данных, в частности в неуправляемых API профилирования и отладки.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="6dbf2-107">ALink</span><span class="sxs-lookup"><span data-stu-id="6dbf2-107">ALink</span></span>](./alink/index.md)  
 <span data-ttu-id="6dbf2-108">Описывает API ALink, поддерживающий создание сборок платформы .NET Framework и несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="6dbf2-109">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6dbf2-109">Authenticode</span></span>](./authenticode/index.md)  
 <span data-ttu-id="6dbf2-110">Поддерживает модуль создания и проверки лицензий Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="6dbf2-111">Константы</span><span class="sxs-lookup"><span data-stu-id="6dbf2-111">Constants</span></span>](constants-unmanaged-api-reference.md)  
 <span data-ttu-id="6dbf2-112">Описывает константы, определяемые в CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 <span data-ttu-id="6dbf2-113">[Пользовательские атрибуты интерфейса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6dbf2-113">[Custom Interface Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span></span>  
 <span data-ttu-id="6dbf2-114">Описывает атрибуты пользовательского интерфейса COM.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="6dbf2-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="6dbf2-115">Debugging</span></span>](./debugging/index.md)  
 <span data-ttu-id="6dbf2-116">Описывает API отладки, позволяющий отладчику производить отладку кода, который выполняется в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="6dbf2-117">Хранилище символов диагностики</span><span class="sxs-lookup"><span data-stu-id="6dbf2-117">Diagnostics Symbol Store</span></span>](./diagnostics/index.md)  
 <span data-ttu-id="6dbf2-118">Описывает API хранилища диагностических символов, который позволяет компилятору генерировать символьную информацию для ее использования отладчиком.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="6dbf2-119">Fusion</span><span class="sxs-lookup"><span data-stu-id="6dbf2-119">Fusion</span></span>](./fusion/index.md)  
 <span data-ttu-id="6dbf2-120">Описывает API переопределения, который позволяет хост-приложению среды выполнения получать доступ к свойствам ресурсов приложения для того, чтобы найти правильные версии этих ресурсов для их применения.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="6dbf2-121">Размещение</span><span class="sxs-lookup"><span data-stu-id="6dbf2-121">Hosting</span></span>](./hosting/index.md)  
 <span data-ttu-id="6dbf2-122">Описывает API размещения, который позволяет неуправляемым узлам интегрировать среду CLR в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="6dbf2-123">Метаданные</span><span class="sxs-lookup"><span data-stu-id="6dbf2-123">Metadata</span></span>](./metadata/index.md)  
 <span data-ttu-id="6dbf2-124">Описывает API метаданных, который позволяет клиенту, например компилятору, генерировать метаданные компонента или получать к ним доступ без загрузки типов средой CLR.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="6dbf2-125">Профилирование</span><span class="sxs-lookup"><span data-stu-id="6dbf2-125">Profiling</span></span>](./profiling/index.md)  
 <span data-ttu-id="6dbf2-126">Описывает API профилирования, который позволяет профилировщику отслеживать выполнение программы с помощью среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="6dbf2-127">Строгое именование</span><span class="sxs-lookup"><span data-stu-id="6dbf2-127">Strong Naming</span></span>](./strong-naming/index.md)  
 <span data-ttu-id="6dbf2-128">Описывает API строгого именования, который позволяет клиенту администрировать подписание строгого именования для сборки.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="6dbf2-129">WMI и счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="6dbf2-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="6dbf2-130">Описывает интерфейсы API, которые упаковывают вызовы библиотек инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="6dbf2-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="6dbf2-131">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="6dbf2-131">Tlbexp Helper Functions</span></span>](./tlbexp/index.md)  
 <span data-ttu-id="6dbf2-132">Описывает две вспомогательные функции и интерфейс, используемые модулем экспорта библиотек (Tlbexp.exe) в процессе преобразования сборки в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6dbf2-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6dbf2-133">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6dbf2-133">Related Sections</span></span>  
 [<span data-ttu-id="6dbf2-134">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="6dbf2-134">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
