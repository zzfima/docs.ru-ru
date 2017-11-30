---
title: "Оболочки COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 733d7f3e56b8ed704003ca9d6c2aa858c713df93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="com-wrappers"></a><span data-ttu-id="51ea1-102">Оболочки COM</span><span class="sxs-lookup"><span data-stu-id="51ea1-102">COM Wrappers</span></span>
<span data-ttu-id="51ea1-103">Модель COM имеет несколько важных отличий от объектной модели .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="51ea1-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
-   <span data-ttu-id="51ea1-104">Клиенты COM-объектов должны управлять временем существования этих объектов. В общеязыковой среде выполнения управление временем существования объектов осуществляет сама среда.</span><span class="sxs-lookup"><span data-stu-id="51ea1-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
-   <span data-ttu-id="51ea1-105">Клиенты COM-объектов определяют доступность службы, запрашивая интерфейс, который ее предоставляет, в результате чего возвращается или не возвращается указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="51ea1-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="51ea1-106">Клиенты объектов .NET могут получать описание функциональных возможностей объекта с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="51ea1-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
-   <span data-ttu-id="51ea1-107">Объекты .NET располагаются в памяти под управлением среды выполнения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51ea1-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="51ea1-108">Среда выполнения может перемещать объекты в памяти в целях оптимизации производительности и обновлять все ссылки на перемещаемые объекты.</span><span class="sxs-lookup"><span data-stu-id="51ea1-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="51ea1-109">Неуправляемые клиенты после получения указателя на объект работают с объектом, находящимся в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="51ea1-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="51ea1-110">У этих клиентов отсутствуют механизмы для работы с объектами, не имеющими фиксированного расположения.</span><span class="sxs-lookup"><span data-stu-id="51ea1-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="51ea1-111">Чтобы обойти эти различия, среда выполнения предоставляет классы-оболочки, которые моделируют вызов объектов в соответствующих им средах для управляемых и неуправляемых клиентов.</span><span class="sxs-lookup"><span data-stu-id="51ea1-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="51ea1-112">Каждый раз, когда управляемый клиент вызывает метод для COM-объекта, среда выполнения создает [вызываемую оболочку времени выполнения](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="51ea1-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="51ea1-113">Помимо прочего, вызываемая оболочка времени выполнения позволяет абстрагировать различия между управляемыми и неуправляемыми механизмами ссылок.</span><span class="sxs-lookup"><span data-stu-id="51ea1-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="51ea1-114">Среда выполнения также создает [вызываемую оболочку COM](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) для работы в обратном направлении, когда COM-клиенту требуется вызвать метод для объекта .NET.</span><span class="sxs-lookup"><span data-stu-id="51ea1-114">The runtime also creates a [COM callable wrapper](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="51ea1-115">Как показано на следующем рисунке, класс-оболочка, который создается средой выполнения, зависит от контекста вызывающего кода.</span><span class="sxs-lookup"><span data-stu-id="51ea1-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 <span data-ttu-id="51ea1-116">![Общие сведения об оболочках COM](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")</span><span class="sxs-lookup"><span data-stu-id="51ea1-116">![COM wrapper overview](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")</span></span>  
<span data-ttu-id="51ea1-117">Общие сведения об оболочках COM</span><span class="sxs-lookup"><span data-stu-id="51ea1-117">COM wrapper overview</span></span>  
  
 <span data-ttu-id="51ea1-118">В большинстве случаев стандартная вызываемая оболочка времени выполнения или вызываемая оболочка COM, создаваемая средой выполнения, реализует маршалинг вызовов, которые выполняются между средами COM и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51ea1-118">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="51ea1-119">С помощью настраиваемых атрибутов при необходимости можно определить способ представления управляемого и неуправляемого кода в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="51ea1-119">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ea1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="51ea1-120">See Also</span></span>  
 [<span data-ttu-id="51ea1-121">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="51ea1-121">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="51ea1-122">Вызываемая оболочка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="51ea1-122">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="51ea1-123">Вызываемая оболочка COM</span><span class="sxs-lookup"><span data-stu-id="51ea1-123">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)  
 [<span data-ttu-id="51ea1-124">Настройка стандартных оболочек</span><span class="sxs-lookup"><span data-stu-id="51ea1-124">Customizing Standard Wrappers</span></span>](http://msdn.microsoft.com/en-us/c40d089b-6a3c-41b5-a20d-d760c215e49d)  
 [<span data-ttu-id="51ea1-125">Практическое руководство. Настройка вызываемых оболочек времени выполнения</span><span class="sxs-lookup"><span data-stu-id="51ea1-125">How to: Customize Runtime Callable Wrappers</span></span>](http://msdn.microsoft.com/en-us/4a4bb3da-4d60-4517-99f2-78d46a681732)
