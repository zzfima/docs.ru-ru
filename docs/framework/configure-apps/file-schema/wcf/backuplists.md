---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: fc9c697aff2e9c26c7922a0acaf5577b0dea2dc1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532374"
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="269e7-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="269e7-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="269e7-103">Представляет раздел конфигурации для определения набора резервных служб, используемых при обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="269e7-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="269e7-104">Каждый дочерний элемент является резервный список, в котором перечислен набор конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="269e7-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="269e7-105">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="269e7-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="269e7-106">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="269e7-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="269e7-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="269e7-107">\<system.serviceModel></span></span>  
<span data-ttu-id="269e7-108">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="269e7-108">\<routing></span></span>  
<span data-ttu-id="269e7-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="269e7-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269e7-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="269e7-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="269e7-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="269e7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="269e7-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="269e7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="269e7-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="269e7-113">Attributes</span></span>  
 <span data-ttu-id="269e7-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="269e7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="269e7-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="269e7-115">Child Elements</span></span>  
  
|<span data-ttu-id="269e7-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="269e7-116">Element</span></span>|<span data-ttu-id="269e7-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="269e7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="269e7-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="269e7-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="269e7-119">Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="269e7-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="269e7-120">.</span><span class="sxs-lookup"><span data-stu-id="269e7-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="269e7-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="269e7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="269e7-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="269e7-122">Element</span></span>|<span data-ttu-id="269e7-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="269e7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="269e7-124">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="269e7-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="269e7-125">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="269e7-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="269e7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="269e7-126">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
