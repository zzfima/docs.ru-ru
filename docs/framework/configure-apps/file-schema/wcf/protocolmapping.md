---
title: '&lt;protocolMapping&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 769ca7b96c3671fdd1b154c99516778f7cbd542e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="59c42-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="59c42-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="59c42-103">Представляет раздел конфигурации определяется набор сопоставления протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, т. д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="59c42-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="59c42-104">При создании конечных точек по умолчанию во время выполнения [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.</span><span class="sxs-lookup"><span data-stu-id="59c42-104">When creating default endpoints at runtime, [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="59c42-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="59c42-105">\<system.serviceModel></span></span>  
<span data-ttu-id="59c42-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="59c42-106">\<protocolMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59c42-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59c42-107">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="59c42-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59c42-108">Attributes and Elements</span></span>  
 <span data-ttu-id="59c42-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="59c42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59c42-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59c42-110">Attributes</span></span>  
 <span data-ttu-id="59c42-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="59c42-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59c42-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59c42-112">Child Elements</span></span>  
  
|<span data-ttu-id="59c42-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="59c42-113">Element</span></span>|<span data-ttu-id="59c42-114">Описание</span><span class="sxs-lookup"><span data-stu-id="59c42-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59c42-115">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="59c42-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="59c42-116">Содержит сопоставление протокола по умолчанию между схемой транспортного протокола (например, http, net.tcp, net.pipe, т. д.) и привязкой WCF.</span><span class="sxs-lookup"><span data-stu-id="59c42-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59c42-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59c42-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59c42-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="59c42-118">Element</span></span>|<span data-ttu-id="59c42-119">Описание</span><span class="sxs-lookup"><span data-stu-id="59c42-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59c42-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59c42-120">system.ServiceModel</span></span>|<span data-ttu-id="59c42-121">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="59c42-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59c42-122">Пример</span><span class="sxs-lookup"><span data-stu-id="59c42-122">Example</span></span>  
 <span data-ttu-id="59c42-123">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="59c42-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="59c42-124">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="59c42-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="59c42-125">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="59c42-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59c42-126">См. также</span><span class="sxs-lookup"><span data-stu-id="59c42-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
