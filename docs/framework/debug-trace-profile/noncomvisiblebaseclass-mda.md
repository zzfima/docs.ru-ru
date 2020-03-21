---
title: nonComVisibleBaseClass MDA
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: 4c16432df201d19b65c91206ec529d07605e979a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181786"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="085db-102">nonComVisibleBaseClass MDA</span><span class="sxs-lookup"><span data-stu-id="085db-102">nonComVisibleBaseClass MDA</span></span>
<span data-ttu-id="085db-103">Помощник по отладке управляемого кода (MDA) `nonComVisibleBaseClass` активируется при вызове `QueryInterface` машинным или управляемым кодом в вызываемой оболочке COM (CSW) видимого для COM управляемого класса, производного от базового класса, невидимого для COM.</span><span class="sxs-lookup"><span data-stu-id="085db-103">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="085db-104">Вызов `QueryInterface` приводит к активации MDA только в тех случаях, когда вызов запрашивает интерфейс класса или `IDispatch` по умолчанию управляемого класса, видимого для COM.</span><span class="sxs-lookup"><span data-stu-id="085db-104">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="085db-105">MDA не активируется, когда `QueryInterface` предназначен для явного интерфейса, который имеет примененный атрибут <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> и явно реализован классом, видимым для COM.</span><span class="sxs-lookup"><span data-stu-id="085db-105">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="085db-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="085db-106">Symptoms</span></span>  
 <span data-ttu-id="085db-107">Вызов `QueryInterface` выполняется из машинного кода, в котором произошел сбой со значением COR_E_INVALIDOPERATION HRESULT.</span><span class="sxs-lookup"><span data-stu-id="085db-107">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="085db-108">Значение HRESULT может возникнуть из-за того, что среда выполнения не разрешает вызовы `QueryInterface`, которые активируют данный MDA.</span><span class="sxs-lookup"><span data-stu-id="085db-108">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="085db-109">Причина</span><span class="sxs-lookup"><span data-stu-id="085db-109">Cause</span></span>  
 <span data-ttu-id="085db-110">Среда выполнения не может разрешить вызовы `QueryInterface` интерфейса класса или интерфейса `IDispatch` по умолчанию видимого для COM класса, производного от класса, невидимого для COM, из-за потенциальных проблем управления версиями.</span><span class="sxs-lookup"><span data-stu-id="085db-110">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="085db-111">Например, если какие-либо открытые члены были добавлены в базовый класс, невидимый для COM, то существующие клиенты COM, использующие производный класс, могут прерваться, поскольку виртуальная таблица производного класса, содержащая члены базового класса, будет изменена в результате такой модификации.</span><span class="sxs-lookup"><span data-stu-id="085db-111">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="085db-112">Явные интерфейсы, предоставляемые в COM, не имеют таких проблем, так как они не включают базовые члены интерфейсов в виртуальной таблице.</span><span class="sxs-lookup"><span data-stu-id="085db-112">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="085db-113">Решение</span><span class="sxs-lookup"><span data-stu-id="085db-113">Resolution</span></span>  
 <span data-ttu-id="085db-114">Не предоставляйте интерфейс класса.</span><span class="sxs-lookup"><span data-stu-id="085db-114">Do not expose the class interface.</span></span> <span data-ttu-id="085db-115">Определите явный интерфейс и примените к нему атрибут <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="085db-115">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="085db-116">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="085db-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="085db-117">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="085db-117">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="085db-118">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="085db-118">Output</span></span>  
 <span data-ttu-id="085db-119">Далее приводится пример сообщения для вызова `QueryInterface` в видимом для COM классе `Derived`, производном от невидимого для COM класса `Base`.</span><span class="sxs-lookup"><span data-stu-id="085db-119">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```output
A QueryInterface call was made requesting the class interface of COM
visible managed class 'Derived'. However since this class derives from
non COM visible class 'Base', the QueryInterface call will fail. This
is done to prevent the non COM visible base class from being
constrained by the COM versioning rules.
```  
  
## <a name="configuration"></a><span data-ttu-id="085db-120">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="085db-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="085db-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="085db-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="085db-122">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="085db-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="085db-123">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="085db-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
