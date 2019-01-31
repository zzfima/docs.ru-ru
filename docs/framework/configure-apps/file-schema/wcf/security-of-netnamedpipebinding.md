---
title: <security> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: ee2c4161f70c01dc09ac36bbcf6a234f822682d0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265313"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="87f96-102">\<Безопасность > из \<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="87f96-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="87f96-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="87f96-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="87f96-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="87f96-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="87f96-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="87f96-105">\<bindings></span></span>  
<span data-ttu-id="87f96-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="87f96-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="87f96-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="87f96-107">\<binding></span></span>  
<span data-ttu-id="87f96-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="87f96-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f96-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87f96-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87f96-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87f96-110">Attributes and Elements</span></span>  
 <span data-ttu-id="87f96-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87f96-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87f96-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87f96-112">Attributes</span></span>  
  
|<span data-ttu-id="87f96-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="87f96-113">Attribute</span></span>|<span data-ttu-id="87f96-114">Описание</span><span class="sxs-lookup"><span data-stu-id="87f96-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87f96-115">режим</span><span class="sxs-lookup"><span data-stu-id="87f96-115">mode</span></span>|<span data-ttu-id="87f96-116">Задает тип системы безопасности, применяемой к этой привязке.</span><span class="sxs-lookup"><span data-stu-id="87f96-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="87f96-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="87f96-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="87f96-118">-None: Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="87f96-118">-   None: This disables security.</span></span><br /><span data-ttu-id="87f96-119">-Транспорта: Безопасность обеспечивается с помощью базовых функций безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="87f96-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="87f96-120">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="87f96-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="87f96-121">-Значение по умолчанию — транспорта.</span><span class="sxs-lookup"><span data-stu-id="87f96-121">-   The default value is Transport.</span></span> <span data-ttu-id="87f96-122">Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="87f96-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87f96-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87f96-123">Child Elements</span></span>  
  
|<span data-ttu-id="87f96-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="87f96-124">Element</span></span>|<span data-ttu-id="87f96-125">Описание</span><span class="sxs-lookup"><span data-stu-id="87f96-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87f96-126">транспорт</span><span class="sxs-lookup"><span data-stu-id="87f96-126">transport</span></span>|<span data-ttu-id="87f96-127">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="87f96-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="87f96-128">Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="87f96-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87f96-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87f96-129">Parent Elements</span></span>  
  
|<span data-ttu-id="87f96-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="87f96-130">Element</span></span>|<span data-ttu-id="87f96-131">Описание</span><span class="sxs-lookup"><span data-stu-id="87f96-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87f96-132">привязка</span><span class="sxs-lookup"><span data-stu-id="87f96-132">binding</span></span>|<span data-ttu-id="87f96-133">Элемент привязки [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="87f96-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87f96-134">См. также</span><span class="sxs-lookup"><span data-stu-id="87f96-134">See also</span></span>
- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="87f96-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="87f96-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="87f96-136">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="87f96-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="87f96-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="87f96-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="87f96-138">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="87f96-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="87f96-139">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="87f96-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="87f96-140">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="87f96-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
