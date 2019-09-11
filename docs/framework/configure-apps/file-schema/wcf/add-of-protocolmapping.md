---
title: <add> из <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850379"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="65eed-102">\<Добавление > \<> протоколмаппинг</span><span class="sxs-lookup"><span data-stu-id="65eed-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="65eed-103">Представляет сопоставление протокола по умолчанию между схемой транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязкой Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="65eed-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="65eed-104">При создании конечных точек по умолчанию во время выполнения WCF проверяет настроенные сопоставления и решает, какая привязка будет использоваться для конкретного адреса на основе.</span><span class="sxs-lookup"><span data-stu-id="65eed-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="65eed-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="65eed-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="65eed-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="65eed-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="65eed-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Протоколмаппинг >** ](protocolmapping.md)</span><span class="sxs-lookup"><span data-stu-id="65eed-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)</span></span>\
<span data-ttu-id="65eed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="65eed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65eed-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65eed-109">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65eed-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="65eed-110">Attributes and Elements</span></span>  
 <span data-ttu-id="65eed-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="65eed-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65eed-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65eed-112">Attributes</span></span>  
  
|<span data-ttu-id="65eed-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="65eed-113">Element</span></span>|<span data-ttu-id="65eed-114">Описание</span><span class="sxs-lookup"><span data-stu-id="65eed-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65eed-115">привязка</span><span class="sxs-lookup"><span data-stu-id="65eed-115">binding</span></span>|<span data-ttu-id="65eed-116">Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65eed-116">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="65eed-117">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="65eed-117">bindingConfiguration</span></span>|<span data-ttu-id="65eed-118">Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.</span><span class="sxs-lookup"><span data-stu-id="65eed-118">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="65eed-119">scheme</span><span class="sxs-lookup"><span data-stu-id="65eed-119">scheme</span></span>|<span data-ttu-id="65eed-120">Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65eed-120">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65eed-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65eed-121">Child Elements</span></span>  
 <span data-ttu-id="65eed-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="65eed-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65eed-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="65eed-123">Parent Elements</span></span>  
  
|<span data-ttu-id="65eed-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="65eed-124">Element</span></span>|<span data-ttu-id="65eed-125">Описание</span><span class="sxs-lookup"><span data-stu-id="65eed-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65eed-126">\<Протоколмаппинг ></span><span class="sxs-lookup"><span data-stu-id="65eed-126">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="65eed-127">Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязками Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="65eed-127">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="65eed-128">Пример</span><span class="sxs-lookup"><span data-stu-id="65eed-128">Example</span></span>  
 <span data-ttu-id="65eed-129">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="65eed-129">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="65eed-130">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="65eed-130">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="65eed-131">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="65eed-131">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65eed-132">См. также</span><span class="sxs-lookup"><span data-stu-id="65eed-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
