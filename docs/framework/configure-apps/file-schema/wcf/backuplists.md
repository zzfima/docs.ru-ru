---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 6e44dbe3c0966c6d243db343b9f9b0dec2480cb1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134450"
---
# <a name="backuplists"></a><span data-ttu-id="e09d8-101">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="e09d8-101">\<backupLists></span></span>
<span data-ttu-id="e09d8-102">Представляет раздел конфигурации для определения набора резервных служб, используемых при обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="e09d8-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="e09d8-103">Каждый дочерний элемент является резервный список, в котором перечислен набор конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="e09d8-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="e09d8-104">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="e09d8-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="e09d8-105">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="e09d8-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="e09d8-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e09d8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e09d8-107">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="e09d8-107">\<routing></span></span>  
<span data-ttu-id="e09d8-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="e09d8-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e09d8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e09d8-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e09d8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e09d8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e09d8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e09d8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e09d8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e09d8-112">Attributes</span></span>  
 <span data-ttu-id="e09d8-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e09d8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e09d8-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e09d8-114">Child Elements</span></span>  
  
|<span data-ttu-id="e09d8-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e09d8-115">Element</span></span>|<span data-ttu-id="e09d8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e09d8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e09d8-117">\<Фильтр ></span><span class="sxs-lookup"><span data-stu-id="e09d8-117">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="e09d8-118">Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="e09d8-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="e09d8-119">.</span><span class="sxs-lookup"><span data-stu-id="e09d8-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e09d8-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e09d8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e09d8-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e09d8-121">Element</span></span>|<span data-ttu-id="e09d8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e09d8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e09d8-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="e09d8-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e09d8-124">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="e09d8-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e09d8-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e09d8-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
