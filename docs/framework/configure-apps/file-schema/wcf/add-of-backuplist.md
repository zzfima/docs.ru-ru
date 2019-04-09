---
title: <add> из <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089540"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="462d4-102">\<Добавить > из \<backupList ></span><span class="sxs-lookup"><span data-stu-id="462d4-102">\<add> of \<backupList></span></span>
<span data-ttu-id="462d4-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="462d4-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="462d4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="462d4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="462d4-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="462d4-105">\<routing></span></span>  
<span data-ttu-id="462d4-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="462d4-106">\<backupLists></span></span>  
<span data-ttu-id="462d4-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="462d4-107">\<backupList></span></span>  
<span data-ttu-id="462d4-108">\<add></span><span class="sxs-lookup"><span data-stu-id="462d4-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="462d4-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="462d4-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="462d4-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="462d4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="462d4-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="462d4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="462d4-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="462d4-112">Attributes</span></span>  
  
|<span data-ttu-id="462d4-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="462d4-113">Attribute</span></span>|<span data-ttu-id="462d4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="462d4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="462d4-115">имя</span><span class="sxs-lookup"><span data-stu-id="462d4-115">name</span></span>|<span data-ttu-id="462d4-116">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="462d4-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="462d4-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="462d4-117">Child Elements</span></span>  
 <span data-ttu-id="462d4-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="462d4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="462d4-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="462d4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="462d4-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="462d4-120">Element</span></span>|<span data-ttu-id="462d4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="462d4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="462d4-122">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="462d4-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="462d4-123">Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="462d4-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="462d4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="462d4-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
