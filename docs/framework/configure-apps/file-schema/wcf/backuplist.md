---
title: '&lt;BackupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 1a6a7ac42b379dd8fb2ba80cf6a3a38998c26a59
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146554"
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="71833-102">&lt;BackupList&gt;</span><span class="sxs-lookup"><span data-stu-id="71833-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="71833-103">Представляет раздел конфигурации для определения резервного списка, который перечисляет набор конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="71833-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="71833-104">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="71833-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="71833-105">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="71833-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="71833-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="71833-106">\<system.serviceModel></span></span>  
<span data-ttu-id="71833-107">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="71833-107">\<routing></span></span>  
<span data-ttu-id="71833-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="71833-108">\<backupLists></span></span>  
<span data-ttu-id="71833-109">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="71833-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71833-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71833-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71833-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="71833-111">Attributes and Elements</span></span>  
 <span data-ttu-id="71833-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="71833-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71833-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71833-113">Attributes</span></span>  
  
|<span data-ttu-id="71833-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="71833-114">Attribute</span></span>|<span data-ttu-id="71833-115">Описание</span><span class="sxs-lookup"><span data-stu-id="71833-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71833-116">имя</span><span class="sxs-lookup"><span data-stu-id="71833-116">name</span></span>|<span data-ttu-id="71833-117">Строка, в которой приведено имя, используемое для указания этого списка конечных точек.</span><span class="sxs-lookup"><span data-stu-id="71833-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71833-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="71833-118">Child Elements</span></span>  
  
|<span data-ttu-id="71833-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="71833-119">Element</span></span>|<span data-ttu-id="71833-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="71833-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71833-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="71833-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="71833-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="71833-122">Parent Elements</span></span>  
  
|<span data-ttu-id="71833-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="71833-123">Element</span></span>|<span data-ttu-id="71833-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="71833-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71833-125">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="71833-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="71833-126">Список резервных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="71833-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71833-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="71833-127">Remarks</span></span>  
 <span data-ttu-id="71833-128">Этот раздел содержит упорядоченную коллекцию конечных точек, в которые будет передаваться сообщение в случае, если при отправке в основную конечную точку возникает исключение связи.</span><span class="sxs-lookup"><span data-stu-id="71833-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="71833-129">Если отправка в основную конечную точку в списке в `endpointName` атрибут [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) завершается ошибкой с исключением связи, служба маршрутизации попытается отправить сообщение в первую конечную точку в этом раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="71833-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="71833-130">Если эта отправка также приведет к возникновению исключения связи, служба маршрутизации попытается отправить сообщение в следующую точку, указанную в этом разделе, пока отправка не завершится успешно или не возвратит ошибку, не связанную с исключением связи, либо пока ошибки не будут возвращены для всех конечных точек из коллекции.</span><span class="sxs-lookup"><span data-stu-id="71833-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="71833-131">В следующем примере Если отправка в основную конечную точку с именем «Destination» возвращает исключение связи, служба попытается отправить сообщение в alternateServiceQueue «».</span><span class="sxs-lookup"><span data-stu-id="71833-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="71833-132">Если эта попытка также возвращает исключение связи, то служба маршрутизации попытается отправить сообщение в следующую конечную точку в коллекции.</span><span class="sxs-lookup"><span data-stu-id="71833-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="71833-133">См. также</span><span class="sxs-lookup"><span data-stu-id="71833-133">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
