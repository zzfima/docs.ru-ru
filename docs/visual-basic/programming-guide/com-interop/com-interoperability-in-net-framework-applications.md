---
title: "COM-взаимодействие в приложениях .NET Framework (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6b68f35c1c63e2d7d229f89336b86c4a062e5ec9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="45469-102">COM-взаимодействие в приложениях .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45469-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="45469-103">Если вы хотите использовать объекты COM и .NET Framework в одном приложении, необходимо учитывать различия в расположении этих объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="45469-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="45469-104">Объект .NET Framework располагается в управляемой памяти, памяти, управляемой средой CLR и при необходимости может быть перемещен средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="45469-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="45469-105">Объект COM располагается в неуправляемой памяти и не планируется переместить в другое расположение в памяти.</span><span class="sxs-lookup"><span data-stu-id="45469-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="45469-106">и [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] предоставляют средства для управления взаимодействием таких управляемых и неуправляемых компонентов.</span><span class="sxs-lookup"><span data-stu-id="45469-106"> and the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="45469-107">Дополнительные сведения об управляемом коде см. в разделе [общеязыковая среда выполнения](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span><span class="sxs-lookup"><span data-stu-id="45469-107">For more information about managed code, see [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span></span>  
  
 <span data-ttu-id="45469-108">В дополнение к использованию объектов COM в приложениях .NET, можно также использовать [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для разработки объектов, доступных из неуправляемого кода через COM.</span><span class="sxs-lookup"><span data-stu-id="45469-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="45469-109">Ссылки на этой странице приведены сведения о взаимодействии между объектами COM и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45469-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="45469-110">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="45469-110">Related Sections</span></span>  
 [<span data-ttu-id="45469-111">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="45469-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="45469-112">Ссылки на разделы, посвященные взаимодействию COM в Visual Basic, включая объекты COM, элементы управления ActiveX, DLL-библиотеки Win32, управляемые объекты и наследование объектов COM.</span><span class="sxs-lookup"><span data-stu-id="45469-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="45469-113">Ошибка оболочки COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="45469-113">COM Interop Wrapper Error</span></span>](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="45469-114">Описание последствий и альтернатив при невозможности создания программы-оболочки взаимодействия COM для конкретного компонента.</span><span class="sxs-lookup"><span data-stu-id="45469-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="45469-115">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="45469-115">Interoperating with Unmanaged Code</span></span>](https://msdn.microsoft.com/library/sd10k43k)  
 <span data-ttu-id="45469-116">Краткое описание некоторых проблем взаимодействия между управляемым и неуправляемым кодом и ссылки для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="45469-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="45469-117">Оболочки COM</span><span class="sxs-lookup"><span data-stu-id="45469-117">COM Wrappers</span></span>](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 <span data-ttu-id="45469-118">Описание вызываемых оболочек времени выполнения, которые позволяют управляемому коду вызывать методы COM, и вызываемых оболочек COM, позволяющих клиентам COM вызывать методы объекта .NET.</span><span class="sxs-lookup"><span data-stu-id="45469-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="45469-119">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="45469-119">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="45469-120">Ссылки на разделы, посвященные COM-взаимодействию оболочки, исключения, наследования, работа с потоками, событий, преобразований и маршалинг.</span><span class="sxs-lookup"><span data-stu-id="45469-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="45469-121">Tlbimp.exe (программа импорта библиотек типов)</span><span class="sxs-lookup"><span data-stu-id="45469-121">Tlbimp.exe (Type Library Importer)</span></span>](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 <span data-ttu-id="45469-122">Описывает средства, которые можно использовать для преобразования определения типов, найденные в библиотеке типов COM, в эквивалентные определения сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="45469-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
