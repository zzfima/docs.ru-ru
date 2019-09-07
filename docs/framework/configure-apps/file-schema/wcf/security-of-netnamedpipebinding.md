---
title: <security> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: cd3ff5d3983283f9b4783912b4b9525c5000df61
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399827"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="38a5b-102">\<> безопасности > \<NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="38a5b-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="38a5b-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="38a5b-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="38a5b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38a5b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38a5b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="38a5b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="38a5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="38a5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="38a5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="38a5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="38a5b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="38a5b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="38a5b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="38a5b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a5b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38a5b-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38a5b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38a5b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="38a5b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38a5b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38a5b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38a5b-113">Attributes</span></span>  
  
|<span data-ttu-id="38a5b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="38a5b-114">Attribute</span></span>|<span data-ttu-id="38a5b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="38a5b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38a5b-116">режим</span><span class="sxs-lookup"><span data-stu-id="38a5b-116">mode</span></span>|<span data-ttu-id="38a5b-117">Задает тип системы безопасности, применяемой к этой привязке.</span><span class="sxs-lookup"><span data-stu-id="38a5b-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="38a5b-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="38a5b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="38a5b-119">None Это отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="38a5b-119">-   None: This disables security.</span></span><br /><span data-ttu-id="38a5b-120">Перемещения Безопасность обеспечивается с помощью базовой безопасности на основе транспорта.</span><span class="sxs-lookup"><span data-stu-id="38a5b-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="38a5b-121">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="38a5b-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="38a5b-122">— Значение по умолчанию — Transport.</span><span class="sxs-lookup"><span data-stu-id="38a5b-122">-   The default value is Transport.</span></span> <span data-ttu-id="38a5b-123">Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="38a5b-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38a5b-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38a5b-124">Child Elements</span></span>  
  
|<span data-ttu-id="38a5b-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="38a5b-125">Element</span></span>|<span data-ttu-id="38a5b-126">Описание</span><span class="sxs-lookup"><span data-stu-id="38a5b-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38a5b-127">транспорт</span><span class="sxs-lookup"><span data-stu-id="38a5b-127">transport</span></span>|<span data-ttu-id="38a5b-128">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="38a5b-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="38a5b-129">Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="38a5b-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38a5b-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38a5b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="38a5b-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="38a5b-131">Element</span></span>|<span data-ttu-id="38a5b-132">Описание</span><span class="sxs-lookup"><span data-stu-id="38a5b-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38a5b-133">привязка</span><span class="sxs-lookup"><span data-stu-id="38a5b-133">binding</span></span>|<span data-ttu-id="38a5b-134">[ Элемент\<Binding > NetNamedPipeBinding](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="38a5b-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38a5b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="38a5b-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="38a5b-136">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="38a5b-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="38a5b-137">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="38a5b-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="38a5b-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="38a5b-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="38a5b-139">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="38a5b-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="38a5b-140">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="38a5b-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="38a5b-141">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="38a5b-141">\<binding></span></span>](../../../misc/binding.md)
