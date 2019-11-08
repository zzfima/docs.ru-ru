---
title: <security> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736433"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="cba44-102">\<> безопасности \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="cba44-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="cba44-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="cba44-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="cba44-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cba44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cba44-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cba44-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cba44-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="cba44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="cba44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="cba44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="cba44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="cba44-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cba44-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="cba44-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba44-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cba44-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cba44-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cba44-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cba44-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cba44-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cba44-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cba44-113">Attributes</span></span>  
  
|<span data-ttu-id="cba44-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cba44-114">Attribute</span></span>|<span data-ttu-id="cba44-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cba44-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cba44-116">режим</span><span class="sxs-lookup"><span data-stu-id="cba44-116">mode</span></span>|<span data-ttu-id="cba44-117">Задает тип системы безопасности, применяемой к этой привязке.</span><span class="sxs-lookup"><span data-stu-id="cba44-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="cba44-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="cba44-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cba44-119">-None: отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="cba44-119">-   None: This disables security.</span></span><br /><span data-ttu-id="cba44-120">-Transport. безопасность обеспечивается с помощью базовой безопасности на основе транспорта.</span><span class="sxs-lookup"><span data-stu-id="cba44-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="cba44-121">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="cba44-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="cba44-122">— Значение по умолчанию — Transport.</span><span class="sxs-lookup"><span data-stu-id="cba44-122">-   The default value is Transport.</span></span> <span data-ttu-id="cba44-123">Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cba44-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cba44-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cba44-124">Child Elements</span></span>  
  
|<span data-ttu-id="cba44-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="cba44-125">Element</span></span>|<span data-ttu-id="cba44-126">Описание</span><span class="sxs-lookup"><span data-stu-id="cba44-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cba44-127">транспорт</span><span class="sxs-lookup"><span data-stu-id="cba44-127">transport</span></span>|<span data-ttu-id="cba44-128">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="cba44-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="cba44-129">Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="cba44-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cba44-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cba44-130">Parent Elements</span></span>  
  
|<span data-ttu-id="cba44-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="cba44-131">Element</span></span>|<span data-ttu-id="cba44-132">Описание</span><span class="sxs-lookup"><span data-stu-id="cba44-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cba44-133">привязка</span><span class="sxs-lookup"><span data-stu-id="cba44-133">binding</span></span>|<span data-ttu-id="cba44-134">Элемент Binding [\<> NetNamedPipeBinding](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="cba44-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cba44-135">См. также</span><span class="sxs-lookup"><span data-stu-id="cba44-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="cba44-136">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cba44-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cba44-137">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="cba44-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="cba44-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="cba44-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cba44-139">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="cba44-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cba44-140">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cba44-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cba44-141">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="cba44-141">\<binding></span></span>](bindings.md)
