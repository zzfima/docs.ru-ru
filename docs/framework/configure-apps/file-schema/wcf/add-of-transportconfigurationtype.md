---
title: "&lt;add&gt; для &lt;transportConfigurationType&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b52345ae30ab56a6f34d2aa46f9836d67555b15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="e5b23-102">&lt;add&gt; для &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="e5b23-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="e5b23-103">Данный элемент представляет собой пару ключ/значение, которая идентифицирует тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="e5b23-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="e5b23-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e5b23-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5b23-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e5b23-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="e5b23-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e5b23-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="e5b23-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e5b23-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b23-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5b23-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5b23-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5b23-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e5b23-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5b23-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5b23-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5b23-111">Attributes</span></span>  
  
|<span data-ttu-id="e5b23-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e5b23-112">Attribute</span></span>|<span data-ttu-id="e5b23-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e5b23-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5b23-114">имя</span><span class="sxs-lookup"><span data-stu-id="e5b23-114">name</span></span>|<span data-ttu-id="e5b23-115">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="e5b23-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="e5b23-116">Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="e5b23-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="e5b23-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="e5b23-117">transportConfigurationType</span></span>|<span data-ttu-id="e5b23-118">Строка, содержащая тип, реализующий конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="e5b23-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5b23-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5b23-119">Child Elements</span></span>  
 <span data-ttu-id="e5b23-120">Нет</span><span class="sxs-lookup"><span data-stu-id="e5b23-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5b23-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5b23-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e5b23-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5b23-122">Element</span></span>|<span data-ttu-id="e5b23-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="e5b23-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5b23-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e5b23-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="e5b23-125">Коллекция типов, реализующих конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="e5b23-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5b23-126">Пример</span><span class="sxs-lookup"><span data-stu-id="e5b23-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5b23-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e5b23-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="e5b23-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="e5b23-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
