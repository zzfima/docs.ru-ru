---
title: '&lt;add&gt; для &lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: e21c3ca665d6a75394d70da43ec2044e00f16429
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145488"
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a><span data-ttu-id="57932-102">&lt;add&gt; для &lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="57932-102">&lt;add&gt; of &lt;protocolMapping&gt;</span></span>
<span data-ttu-id="57932-103">Представляет сопоставление протокола по умолчанию между схемой транспортного протокола (например, http, net.tcp, net.pipe, и т.д.) и привязкой Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="57932-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="57932-104">При создании конечных точек по умолчанию во время выполнения, WCF просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.</span><span class="sxs-lookup"><span data-stu-id="57932-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="57932-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="57932-105">\<system.serviceModel></span></span>  
<span data-ttu-id="57932-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="57932-106">\<protocolMapping></span></span>  
<span data-ttu-id="57932-107">\<add></span><span class="sxs-lookup"><span data-stu-id="57932-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57932-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57932-108">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57932-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="57932-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57932-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="57932-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57932-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57932-111">Attributes</span></span>  
  
|<span data-ttu-id="57932-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="57932-112">Element</span></span>|<span data-ttu-id="57932-113">Описание</span><span class="sxs-lookup"><span data-stu-id="57932-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57932-114">привязка</span><span class="sxs-lookup"><span data-stu-id="57932-114">binding</span></span>|<span data-ttu-id="57932-115">Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57932-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="57932-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="57932-116">bindingConfiguration</span></span>|<span data-ttu-id="57932-117">Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.</span><span class="sxs-lookup"><span data-stu-id="57932-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="57932-118">scheme</span><span class="sxs-lookup"><span data-stu-id="57932-118">scheme</span></span>|<span data-ttu-id="57932-119">Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57932-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57932-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57932-120">Child Elements</span></span>  
 <span data-ttu-id="57932-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57932-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57932-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57932-122">Parent Elements</span></span>  
  
|<span data-ttu-id="57932-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="57932-123">Element</span></span>|<span data-ttu-id="57932-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="57932-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57932-125">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="57932-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="57932-126">Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, и т.д.) и привязками Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="57932-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="57932-127">Пример</span><span class="sxs-lookup"><span data-stu-id="57932-127">Example</span></span>  
 <span data-ttu-id="57932-128">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="57932-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="57932-129">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="57932-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="57932-130">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="57932-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57932-131">См. также</span><span class="sxs-lookup"><span data-stu-id="57932-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
