---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918711"
---
# <a name="host"></a><span data-ttu-id="f5781-101">\<> узла</span><span class="sxs-lookup"><span data-stu-id="f5781-101">\<host></span></span>
<span data-ttu-id="f5781-102">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="f5781-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="f5781-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f5781-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f5781-104">\<службы ></span><span class="sxs-lookup"><span data-stu-id="f5781-104">\<services></span></span>  
<span data-ttu-id="f5781-105">\<> службы</span><span class="sxs-lookup"><span data-stu-id="f5781-105">\<service></span></span>  
<span data-ttu-id="f5781-106">\<> узла</span><span class="sxs-lookup"><span data-stu-id="f5781-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5781-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5781-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="f5781-108">Тип</span><span class="sxs-lookup"><span data-stu-id="f5781-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5781-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f5781-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f5781-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f5781-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5781-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f5781-111">Attributes</span></span>  
 <span data-ttu-id="f5781-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f5781-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5781-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f5781-113">Child Elements</span></span>  
  
|<span data-ttu-id="f5781-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5781-114">Element</span></span>|<span data-ttu-id="f5781-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f5781-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5781-116">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="f5781-116">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="f5781-117">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="f5781-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="f5781-118">\<> времени ожидания</span><span class="sxs-lookup"><span data-stu-id="f5781-118">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="f5781-119">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="f5781-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5781-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f5781-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f5781-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5781-121">Element</span></span>|<span data-ttu-id="f5781-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f5781-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5781-123">\<> службы</span><span class="sxs-lookup"><span data-stu-id="f5781-123">\<service></span></span>](service.md)|<span data-ttu-id="f5781-124">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f5781-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5781-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f5781-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="f5781-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="f5781-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
