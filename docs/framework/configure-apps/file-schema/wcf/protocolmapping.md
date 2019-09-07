---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400025"
---
# <a name="protocolmapping"></a><span data-ttu-id="e2b7f-101">\<Протоколмаппинг ></span><span class="sxs-lookup"><span data-stu-id="e2b7f-101">\<protocolMapping></span></span>
<span data-ttu-id="e2b7f-102">Представляет раздел конфигурации для определения набора сопоставлений протоколов по умолчанию между схемами транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="e2b7f-103">При создании конечных точек по умолчанию во время выполнения Windows Communication Foundation (WCF) рассматривает настроенные сопоставления и решает, какую привязку использовать для конкретного адреса на основе.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="e2b7f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2b7f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2b7f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e2b7f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e2b7f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Протоколмаппинг >**</span><span class="sxs-lookup"><span data-stu-id="e2b7f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b7f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2b7f-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2b7f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2b7f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2b7f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2b7f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2b7f-110">Attributes</span></span>  
 <span data-ttu-id="e2b7f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2b7f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2b7f-112">Child Elements</span></span>  
  
|<span data-ttu-id="e2b7f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2b7f-113">Element</span></span>|<span data-ttu-id="e2b7f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e2b7f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b7f-115">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="e2b7f-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="e2b7f-116">Содержит сопоставление протокола по умолчанию между схемой транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязкой WCF.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2b7f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2b7f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e2b7f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2b7f-118">Element</span></span>|<span data-ttu-id="e2b7f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e2b7f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b7f-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e2b7f-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="e2b7f-121">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e2b7f-122">Пример</span><span class="sxs-lookup"><span data-stu-id="e2b7f-122">Example</span></span>  
 <span data-ttu-id="e2b7f-123">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="e2b7f-124">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="e2b7f-125">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="e2b7f-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e2b7f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e2b7f-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
