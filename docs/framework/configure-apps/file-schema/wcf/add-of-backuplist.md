---
title: <add> из <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850550"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="aa4a4-102">\<Добавление > \<> баккуплист</span><span class="sxs-lookup"><span data-stu-id="aa4a4-102">\<add> of \<backupList></span></span>
<span data-ttu-id="aa4a4-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="aa4a4-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="aa4a4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa4a4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa4a4-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aa4a4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aa4a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="aa4a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="aa4a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Баккуплистс >** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="aa4a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="aa4a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Баккуплист >** ](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="aa4a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="aa4a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="aa4a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4a4-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa4a4-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa4a4-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa4a4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aa4a4-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa4a4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa4a4-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa4a4-113">Attributes</span></span>  
  
|<span data-ttu-id="aa4a4-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aa4a4-114">Attribute</span></span>|<span data-ttu-id="aa4a4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aa4a4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa4a4-116">имя</span><span class="sxs-lookup"><span data-stu-id="aa4a4-116">name</span></span>|<span data-ttu-id="aa4a4-117">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="aa4a4-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa4a4-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa4a4-118">Child Elements</span></span>  
 <span data-ttu-id="aa4a4-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="aa4a4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa4a4-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa4a4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="aa4a4-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa4a4-121">Element</span></span>|<span data-ttu-id="aa4a4-122">Описание</span><span class="sxs-lookup"><span data-stu-id="aa4a4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa4a4-123">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="aa4a4-123">\<routing></span></span>](routing.md)|<span data-ttu-id="aa4a4-124">Содержит список конечных точек, которые служба маршрутизации должна использовать в случае, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="aa4a4-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa4a4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="aa4a4-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
