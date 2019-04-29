---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: e26044340bda84fe38b7e286edf833affa94b86c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785493"
---
# <a name="protocolmapping"></a><span data-ttu-id="54a2f-101">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="54a2f-101">\<protocolMapping></span></span>
<span data-ttu-id="54a2f-102">Представляет раздел конфигурации для определения набора сопоставлений протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, и т.д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="54a2f-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="54a2f-103">При создании конечных точек по умолчанию во время выполнения, Windows Communication Foundation (WCF) просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.</span><span class="sxs-lookup"><span data-stu-id="54a2f-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="54a2f-104">**\<system.serviceModel >**</span><span class="sxs-lookup"><span data-stu-id="54a2f-104">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="54a2f-105">&nbsp;&nbsp;**\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="54a2f-105">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54a2f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54a2f-106">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54a2f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="54a2f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="54a2f-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="54a2f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54a2f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="54a2f-109">Attributes</span></span>  
 <span data-ttu-id="54a2f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="54a2f-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="54a2f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="54a2f-111">Child Elements</span></span>  
  
|<span data-ttu-id="54a2f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="54a2f-112">Element</span></span>|<span data-ttu-id="54a2f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="54a2f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54a2f-114">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="54a2f-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="54a2f-115">Содержит сопоставление протокола по умолчанию между схемой транспортного протокола (например, http, net.tcp, net.pipe, и т.д.) и привязкой WCF.</span><span class="sxs-lookup"><span data-stu-id="54a2f-115">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54a2f-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="54a2f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="54a2f-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="54a2f-117">Element</span></span>|<span data-ttu-id="54a2f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="54a2f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54a2f-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="54a2f-119">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="54a2f-120">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="54a2f-120">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="54a2f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="54a2f-121">Example</span></span>  
 <span data-ttu-id="54a2f-122">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="54a2f-122">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="54a2f-123">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="54a2f-123">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="54a2f-124">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="54a2f-124">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54a2f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="54a2f-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
