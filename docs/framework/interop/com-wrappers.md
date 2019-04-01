---
title: Оболочки COM
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce15e0535bbd6bc67054c651a518f11cf9dd2ae1
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410359"
---
# <a name="com-wrappers"></a><span data-ttu-id="f5ed0-102">Оболочки COM</span><span class="sxs-lookup"><span data-stu-id="f5ed0-102">COM Wrappers</span></span>
<span data-ttu-id="f5ed0-103">Модель COM имеет несколько важных отличий от объектной модели .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f5ed0-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
-   <span data-ttu-id="f5ed0-104">Клиенты COM-объектов должны управлять временем существования этих объектов. В общеязыковой среде выполнения управление временем существования объектов осуществляет сама среда.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
-   <span data-ttu-id="f5ed0-105">Клиенты COM-объектов определяют доступность службы, запрашивая интерфейс, который ее предоставляет, в результате чего возвращается или не возвращается указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="f5ed0-106">Клиенты объектов .NET могут получать описание функциональных возможностей объекта с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
-   <span data-ttu-id="f5ed0-107">Объекты .NET располагаются в памяти под управлением среды выполнения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="f5ed0-108">Среда выполнения может перемещать объекты в памяти в целях оптимизации производительности и обновлять все ссылки на перемещаемые объекты.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="f5ed0-109">Неуправляемые клиенты после получения указателя на объект работают с объектом, находящимся в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="f5ed0-110">У этих клиентов отсутствуют механизмы для работы с объектами, не имеющими фиксированного расположения.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="f5ed0-111">Чтобы обойти эти различия, среда выполнения предоставляет классы-оболочки, которые моделируют вызов объектов в соответствующих им средах для управляемых и неуправляемых клиентов.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="f5ed0-112">Каждый раз, когда управляемый клиент вызывает метод для COM-объекта, среда выполнения создает [вызываемую оболочку времени выполнения](runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="f5ed0-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="f5ed0-113">Помимо прочего, вызываемая оболочка времени выполнения позволяет абстрагировать различия между управляемыми и неуправляемыми механизмами ссылок.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="f5ed0-114">Среда выполнения также создает [вызываемую оболочку COM](com-callable-wrapper.md) (CCW) для работы в обратном направлении, когда COM-клиенту требуется вызвать метод для объекта .NET.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-114">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="f5ed0-115">Как показано на следующем рисунке, класс-оболочка, который создается средой выполнения, зависит от контекста вызывающего кода.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 ![Общие сведения об оболочках COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 <span data-ttu-id="f5ed0-117">В большинстве случаев стандартная вызываемая оболочка времени выполнения или вызываемая оболочка COM, создаваемая средой выполнения, реализует маршалинг вызовов, которые выполняются между средами COM и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-117">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="f5ed0-118">С помощью настраиваемых атрибутов при необходимости можно определить способ представления управляемого и неуправляемого кода в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="f5ed0-118">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ed0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f5ed0-119">See also</span></span>
- <span data-ttu-id="f5ed0-120">[Расширенное COM-взаимодействие](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5ed0-120">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="f5ed0-121">Вызываемая оболочка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="f5ed0-121">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
- [<span data-ttu-id="f5ed0-122">Вызываемая оболочка COM</span><span class="sxs-lookup"><span data-stu-id="f5ed0-122">COM Callable Wrapper</span></span>](com-callable-wrapper.md)
- <span data-ttu-id="f5ed0-123">[Customizing Standard Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100)) (Настройка стандартных оболочек)</span><span class="sxs-lookup"><span data-stu-id="f5ed0-123">[Customizing Standard Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span></span>
- <span data-ttu-id="f5ed0-124">[Практическое руководство. Настройка вызываемых оболочек времени выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5ed0-124">[How to: Customize Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span></span>
