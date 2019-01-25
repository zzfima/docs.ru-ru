---
title: '&lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 199a5d820a80565ccdfa2cb11fe749d63bd65087
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644264"
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="bf2bb-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="bf2bb-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="bf2bb-103">Представляет раздел конфигурации для определения набора сопоставлений протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, и т.д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="bf2bb-104">При создании конечных точек по умолчанию во время выполнения, Windows Communication Foundation (WCF) просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-104">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="bf2bb-105">**\<system.serviceModel >**</span><span class="sxs-lookup"><span data-stu-id="bf2bb-105">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="bf2bb-106">&nbsp;&nbsp;**\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="bf2bb-106">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf2bb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf2bb-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf2bb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf2bb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bf2bb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf2bb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf2bb-110">Attributes</span></span>  
 <span data-ttu-id="bf2bb-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf2bb-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf2bb-112">Child Elements</span></span>  
  
|<span data-ttu-id="bf2bb-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf2bb-113">Element</span></span>|<span data-ttu-id="bf2bb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bf2bb-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf2bb-115">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="bf2bb-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="bf2bb-116">Содержит сопоставление протокола по умолчанию между схемой транспортного протокола (например, http, net.tcp, net.pipe, и т.д.) и привязкой WCF.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf2bb-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf2bb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bf2bb-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf2bb-118">Element</span></span>|<span data-ttu-id="bf2bb-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="bf2bb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf2bb-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bf2bb-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="bf2bb-121">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf2bb-122">Пример</span><span class="sxs-lookup"><span data-stu-id="bf2bb-122">Example</span></span>  
 <span data-ttu-id="bf2bb-123">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="bf2bb-124">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="bf2bb-125">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="bf2bb-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="bf2bb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bf2bb-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
