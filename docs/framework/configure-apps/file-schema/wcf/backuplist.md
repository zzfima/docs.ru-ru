---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850269"
---
# <a name="backuplist"></a><span data-ttu-id="9a91d-101">\<Баккуплист ></span><span class="sxs-lookup"><span data-stu-id="9a91d-101">\<backupList></span></span>
<span data-ttu-id="9a91d-102">Представляет раздел конфигурации для определения списка резервных копий, который перечисляет набор конечных точек, которые должны использоваться службой маршрутизации в случае, если основная конечная точка недостижима.</span><span class="sxs-lookup"><span data-stu-id="9a91d-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="9a91d-103">Если первая конечная точка в списке недоступна, то служба маршрутизации автоматически переключается на следующую точку в списке.</span><span class="sxs-lookup"><span data-stu-id="9a91d-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="9a91d-104">Этот метод позволяет быстро повысить надежность приложения, не реализуя в клиентском приложении обработку сложных схем и не задавая расположение всех служб.</span><span class="sxs-lookup"><span data-stu-id="9a91d-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="9a91d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a91d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a91d-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a91d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9a91d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="9a91d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="9a91d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Баккуплистс >** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="9a91d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="9a91d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Баккуплист >**</span><span class="sxs-lookup"><span data-stu-id="9a91d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a91d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a91d-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a91d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9a91d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9a91d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9a91d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a91d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9a91d-113">Attributes</span></span>  
  
|<span data-ttu-id="9a91d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9a91d-114">Attribute</span></span>|<span data-ttu-id="9a91d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9a91d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a91d-116">имя</span><span class="sxs-lookup"><span data-stu-id="9a91d-116">name</span></span>|<span data-ttu-id="9a91d-117">Строка, в которой приведено имя, используемое для указания этого списка конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9a91d-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a91d-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9a91d-118">Child Elements</span></span>  
  
|<span data-ttu-id="9a91d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="9a91d-119">Element</span></span>|<span data-ttu-id="9a91d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9a91d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a91d-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="9a91d-121">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="9a91d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9a91d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9a91d-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9a91d-123">Element</span></span>|<span data-ttu-id="9a91d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="9a91d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a91d-125">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="9a91d-125">\<routing></span></span>](routing.md)|<span data-ttu-id="9a91d-126">Список резервных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9a91d-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a91d-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a91d-127">Remarks</span></span>  
 <span data-ttu-id="9a91d-128">Этот раздел содержит упорядоченную коллекцию конечных точек, в которые будет передаваться сообщение в случае, если при отправке в основную конечную точку возникает исключение связи.</span><span class="sxs-lookup"><span data-stu-id="9a91d-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="9a91d-129">Если отправка в основную конечную точку, указанную `endpointName` в [ \<атрибуте Add >](add-of-entries.md) , завершается с исключением связи, служба Routing Service попытается отправить сообщение в первую конечную точку в этом разделе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9a91d-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="9a91d-130">Если эта отправка также приведет к возникновению исключения связи, служба маршрутизации попытается отправить сообщение в следующую точку, указанную в этом разделе, пока отправка не завершится успешно или не возвратит ошибку, не связанную с исключением связи, либо пока ошибки не будут возвращены для всех конечных точек из коллекции.</span><span class="sxs-lookup"><span data-stu-id="9a91d-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="9a91d-131">В следующем примере, если отправка в основную конечную точку с именем "Destination" возвращает исключение связи, Служба попытается отправить сообщение в "Алтернатесервицекуеуе".</span><span class="sxs-lookup"><span data-stu-id="9a91d-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="9a91d-132">Если эта попытка также возвращает исключение связи, то служба маршрутизации попытается отправить сообщение в следующую конечную точку в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9a91d-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a91d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="9a91d-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
