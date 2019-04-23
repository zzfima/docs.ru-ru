---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 6e44dbe3c0966c6d243db343b9f9b0dec2480cb1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134450"
---
# <a name="backuplists"></a><span data-ttu-id="c6a1c-101">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="c6a1c-101">\<backupLists></span></span>
<span data-ttu-id="c6a1c-102">Представляет раздел конфигурации для определения набора резервных служб, используемых при обработке ошибок.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="c6a1c-103">Каждый дочерний элемент является резервный список, в котором перечислен набор конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="c6a1c-104">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="c6a1c-105">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="c6a1c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c6a1c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c6a1c-107">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="c6a1c-107">\<routing></span></span>  
<span data-ttu-id="c6a1c-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="c6a1c-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6a1c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6a1c-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6a1c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6a1c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c6a1c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6a1c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6a1c-112">Attributes</span></span>  
 <span data-ttu-id="c6a1c-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6a1c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6a1c-114">Child Elements</span></span>  
  
|<span data-ttu-id="c6a1c-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6a1c-115">Element</span></span>|<span data-ttu-id="c6a1c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c6a1c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6a1c-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="c6a1c-117">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="c6a1c-118">Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="c6a1c-119">.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6a1c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6a1c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c6a1c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6a1c-121">Element</span></span>|<span data-ttu-id="c6a1c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c6a1c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6a1c-123">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="c6a1c-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="c6a1c-124">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="c6a1c-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6a1c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c6a1c-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
