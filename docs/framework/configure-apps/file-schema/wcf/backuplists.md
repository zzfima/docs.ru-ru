---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850267"
---
# <a name="backuplists"></a><span data-ttu-id="bb196-101">\<Баккуплистс ></span><span class="sxs-lookup"><span data-stu-id="bb196-101">\<backupLists></span></span>
<span data-ttu-id="bb196-102">Представляет раздел конфигурации для определения набора резервных служб, используемых при обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="bb196-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="bb196-103">Каждый дочерний элемент является списком резервных копий, который перечисляет набор конечных точек, которые должны использоваться службой маршрутизации в случае, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="bb196-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="bb196-104">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="bb196-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="bb196-105">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="bb196-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="bb196-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb196-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bb196-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bb196-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bb196-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="bb196-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="bb196-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Баккуплистс >**</span><span class="sxs-lookup"><span data-stu-id="bb196-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb196-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb196-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb196-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb196-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bb196-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb196-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb196-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb196-113">Attributes</span></span>  
 <span data-ttu-id="bb196-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="bb196-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb196-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb196-115">Child Elements</span></span>  
  
|<span data-ttu-id="bb196-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb196-116">Element</span></span>|<span data-ttu-id="bb196-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bb196-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb196-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="bb196-118">\<filter></span></span>](filter.md)|<span data-ttu-id="bb196-119">Содержит список конечных точек, которые служба маршрутизации должна использовать в случае, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="bb196-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="bb196-120">.</span><span class="sxs-lookup"><span data-stu-id="bb196-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb196-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb196-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bb196-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb196-122">Element</span></span>|<span data-ttu-id="bb196-123">Описание</span><span class="sxs-lookup"><span data-stu-id="bb196-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb196-124">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="bb196-124">\<routing></span></span>](routing.md)|<span data-ttu-id="bb196-125">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="bb196-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb196-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bb196-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
