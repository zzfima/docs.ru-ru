---
title: "COM-взаимодействие в приложениях .NET Framework (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c84143e22f33f572447c50e33559a52469b181a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="2e7fb-102">COM-взаимодействие в приложениях .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e7fb-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="2e7fb-103">Если вы хотите использовать .NET Framework и COM-объектов в одном приложении, необходимо учитывать различия в расположении этих объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="2e7fb-104">Объект .NET Framework располагается в управляемой памяти, памяти, управляемой средой CLR и при необходимости может быть перемещен средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="2e7fb-105">COM-объект находится в неуправляемой памяти и не планируется переместить в другое расположение в памяти.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="2e7fb-106">и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют средства для управления взаимодействием таких управляемых и неуправляемых компонентов.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-106"> and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="2e7fb-107">Дополнительные сведения об управляемом коде см. в разделе [общеязыковая среда выполнения](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="2e7fb-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="2e7fb-108">В дополнение к использованию объектов COM в приложениях .NET, можно также использовать [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для разработки объектов, доступных из неуправляемого кода через COM.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="2e7fb-109">Ссылки на этой странице приведены сведения о взаимодействии между объектами COM и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2e7fb-110">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2e7fb-110">Related Sections</span></span>  
 [<span data-ttu-id="2e7fb-111">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="2e7fb-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="2e7fb-112">Ссылки на разделы, посвященные COM-взаимодействие в Visual Basic, включая объекты COM, элементы управления ActiveX, DLL-библиотеки Win32, управляемые объекты и наследование COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="2e7fb-113">Ошибка оболочки COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2e7fb-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="2e7fb-114">Описание последствий и параметры, если система проектов не удается создать оболочку COM взаимодействия для конкретного компонента.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="2e7fb-115">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="2e7fb-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="2e7fb-116">Краткое описание некоторых проблем взаимодействия между управляемым и неуправляемым кодом и ссылки для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="2e7fb-117">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="2e7fb-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="2e7fb-118">Описание вызываемых оболочек времени выполнения, которые позволяют управляемому коду вызывать методы COM, и вызываемых оболочек COM, которые позволяют клиентам COM вызывать методы объекта .NET.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="2e7fb-119">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="2e7fb-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="2e7fb-120">Ссылки на разделы, посвященные оболочки, исключения, наследования, работа с потоками, событий, преобразований и маршалинг COM-взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="2e7fb-121">Tlbimp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="2e7fb-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="2e7fb-122">Описывает средства, которые можно использовать для преобразования определений типов, имеющихся в библиотеке типов COM, в эквивалентные определения сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2e7fb-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
