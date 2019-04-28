---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: b0a6c604b5741c1355c35fca510cd10544dab9f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704431"
---
# <a name="backuplist"></a><span data-ttu-id="c3238-101">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="c3238-101">\<backupList></span></span>
<span data-ttu-id="c3238-102">Представляет раздел конфигурации для определения резервного списка, который перечисляет набор конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="c3238-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="c3238-103">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="c3238-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="c3238-104">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="c3238-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="c3238-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c3238-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c3238-106">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="c3238-106">\<routing></span></span>  
<span data-ttu-id="c3238-107">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="c3238-107">\<backupLists></span></span>  
<span data-ttu-id="c3238-108">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="c3238-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3238-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3238-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3238-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c3238-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c3238-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c3238-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3238-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c3238-112">Attributes</span></span>  
  
|<span data-ttu-id="c3238-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c3238-113">Attribute</span></span>|<span data-ttu-id="c3238-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c3238-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3238-115">имя</span><span class="sxs-lookup"><span data-stu-id="c3238-115">name</span></span>|<span data-ttu-id="c3238-116">Строка, в которой приведено имя, используемое для указания этого списка конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c3238-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3238-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c3238-117">Child Elements</span></span>  
  
|<span data-ttu-id="c3238-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c3238-118">Element</span></span>|<span data-ttu-id="c3238-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c3238-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3238-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="c3238-120">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="c3238-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c3238-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c3238-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c3238-122">Element</span></span>|<span data-ttu-id="c3238-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c3238-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3238-124">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="c3238-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="c3238-125">Список резервных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c3238-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3238-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3238-126">Remarks</span></span>  
 <span data-ttu-id="c3238-127">Этот раздел содержит упорядоченную коллекцию конечных точек, в которые будет передаваться сообщение в случае, если при отправке в основную конечную точку возникает исключение связи.</span><span class="sxs-lookup"><span data-stu-id="c3238-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="c3238-128">Если отправка в основную конечную точку в списке в `endpointName` атрибут [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) завершается ошибкой с исключением связи, служба маршрутизации попытается отправить сообщение в первую конечную точку в этом раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3238-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="c3238-129">Если эта отправка также приведет к возникновению исключения связи, служба маршрутизации попытается отправить сообщение в следующую точку, указанную в этом разделе, пока отправка не завершится успешно или не возвратит ошибку, не связанную с исключением связи, либо пока ошибки не будут возвращены для всех конечных точек из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c3238-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="c3238-130">В следующем примере Если отправка в основную конечную точку с именем «Destination» возвращает исключение связи, служба попытается отправить сообщение в alternateServiceQueue «».</span><span class="sxs-lookup"><span data-stu-id="c3238-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="c3238-131">Если эта попытка также возвращает исключение связи, то служба маршрутизации попытается отправить сообщение в следующую конечную точку в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c3238-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="c3238-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c3238-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
