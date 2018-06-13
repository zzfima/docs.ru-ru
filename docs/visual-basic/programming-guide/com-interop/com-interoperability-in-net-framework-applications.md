---
title: COM-взаимодействие в приложениях .NET Framework (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642929"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="b927d-102">COM-взаимодействие в приложениях .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b927d-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="b927d-103">Если вы хотите использовать .NET Framework и COM-объектов в одном приложении, необходимо учитывать различия в расположении этих объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="b927d-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="b927d-104">Объект .NET Framework располагается в управляемой памяти, памяти, управляемой средой CLR и при необходимости может быть перемещен средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="b927d-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="b927d-105">COM-объект находится в неуправляемой памяти и не планируется переместить в другое расположение в памяти.</span><span class="sxs-lookup"><span data-stu-id="b927d-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="b927d-106">Visual Studio и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] предоставляют средства для управления взаимодействием таких управляемых и неуправляемых компонентов.</span><span class="sxs-lookup"><span data-stu-id="b927d-106">Visual Studio and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="b927d-107">Дополнительные сведения об управляемом коде см. в разделе [общеязыковая среда выполнения](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="b927d-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="b927d-108">В дополнение к использованию объектов COM в приложениях .NET, можно также использовать Visual Basic для разработки объектов, доступных из неуправляемого кода через COM.</span><span class="sxs-lookup"><span data-stu-id="b927d-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="b927d-109">Ссылки на этой странице приведены сведения о взаимодействии между объектами COM и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b927d-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b927d-110">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b927d-110">Related Sections</span></span>  
 [<span data-ttu-id="b927d-111">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="b927d-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="b927d-112">Ссылки на разделы, посвященные COM-взаимодействие в Visual Basic, включая объекты COM, элементы управления ActiveX, DLL-библиотеки Win32, управляемые объекты и наследование COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="b927d-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="b927d-113">Ошибка оболочки COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b927d-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="b927d-114">Описание последствий и параметры, если система проектов не удается создать оболочку COM взаимодействия для конкретного компонента.</span><span class="sxs-lookup"><span data-stu-id="b927d-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="b927d-115">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="b927d-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="b927d-116">Краткое описание некоторых проблем взаимодействия между управляемым и неуправляемым кодом и ссылки для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="b927d-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="b927d-117">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="b927d-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="b927d-118">Описание вызываемых оболочек времени выполнения, которые позволяют управляемому коду вызывать методы COM, и вызываемых оболочек COM, которые позволяют клиентам COM вызывать методы объекта .NET.</span><span class="sxs-lookup"><span data-stu-id="b927d-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="b927d-119">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="b927d-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="b927d-120">Ссылки на разделы, посвященные оболочки, исключения, наследования, работа с потоками, событий, преобразований и маршалинг COM-взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="b927d-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="b927d-121">Tlbimp.exe (программа экспорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="b927d-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="b927d-122">Описывает средства, которые можно использовать для преобразования определений типов, имеющихся в библиотеке типов COM, в эквивалентные определения сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b927d-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
