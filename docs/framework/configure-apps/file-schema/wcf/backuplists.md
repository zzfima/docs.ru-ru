---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: b65cc4d04b5304e93b70509c9db3bc2248accb7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926433"
---
# <a name="backuplists"></a><span data-ttu-id="b6116-101">\<Баккуплистс ></span><span class="sxs-lookup"><span data-stu-id="b6116-101">\<backupLists></span></span>
<span data-ttu-id="b6116-102">Представляет раздел конфигурации для определения набора резервных служб, используемых при обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="b6116-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="b6116-103">Каждый дочерний элемент является списком резервных копий, который перечисляет набор конечных точек, которые должны использоваться службой маршрутизации в случае, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="b6116-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="b6116-104">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="b6116-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="b6116-105">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="b6116-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="b6116-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="b6116-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b6116-107">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="b6116-107">\<routing></span></span>  
<span data-ttu-id="b6116-108">\<Баккуплистс ></span><span class="sxs-lookup"><span data-stu-id="b6116-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6116-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6116-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6116-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6116-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b6116-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6116-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6116-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6116-112">Attributes</span></span>  
 <span data-ttu-id="b6116-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="b6116-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6116-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6116-114">Child Elements</span></span>  
  
|<span data-ttu-id="b6116-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6116-115">Element</span></span>|<span data-ttu-id="b6116-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b6116-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6116-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="b6116-117">\<filter></span></span>](filter.md)|<span data-ttu-id="b6116-118">Содержит список конечных точек, которые служба маршрутизации должна использовать в случае, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="b6116-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="b6116-119">.</span><span class="sxs-lookup"><span data-stu-id="b6116-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6116-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6116-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b6116-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6116-121">Element</span></span>|<span data-ttu-id="b6116-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b6116-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6116-123">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="b6116-123">\<routing></span></span>](routing.md)|<span data-ttu-id="b6116-124">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="b6116-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6116-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b6116-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
