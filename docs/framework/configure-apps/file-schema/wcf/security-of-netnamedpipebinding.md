---
title: "&lt;security&gt; для &lt;netNamedPipeBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3a018c502aead84eb6936001acb5bc24c59188f8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="053d7-102">&lt;security&gt; для &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="053d7-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="053d7-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="053d7-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="053d7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="053d7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="053d7-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="053d7-105">\<bindings></span></span>  
<span data-ttu-id="053d7-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="053d7-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="053d7-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="053d7-107">\<binding></span></span>  
<span data-ttu-id="053d7-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="053d7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053d7-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="053d7-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="053d7-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="053d7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="053d7-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="053d7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="053d7-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="053d7-112">Attributes</span></span>  
  
|<span data-ttu-id="053d7-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="053d7-113">Attribute</span></span>|<span data-ttu-id="053d7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="053d7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="053d7-115">режим</span><span class="sxs-lookup"><span data-stu-id="053d7-115">mode</span></span>|<span data-ttu-id="053d7-116">Задает тип системы безопасности, применяемой к этой привязке.</span><span class="sxs-lookup"><span data-stu-id="053d7-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="053d7-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="053d7-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="053d7-118">— None: Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="053d7-118">-   None: This disables security.</span></span><br /><span data-ttu-id="053d7-119">-Transport: Безопасность обеспечивается с помощью базовых функций безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="053d7-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="053d7-120">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="053d7-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="053d7-121">Значение по умолчанию-Transport.</span><span class="sxs-lookup"><span data-stu-id="053d7-121">-   The default value is Transport.</span></span> <span data-ttu-id="053d7-122">Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="053d7-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="053d7-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="053d7-123">Child Elements</span></span>  
  
|<span data-ttu-id="053d7-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="053d7-124">Element</span></span>|<span data-ttu-id="053d7-125">Описание</span><span class="sxs-lookup"><span data-stu-id="053d7-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="053d7-126">транспорт</span><span class="sxs-lookup"><span data-stu-id="053d7-126">transport</span></span>|<span data-ttu-id="053d7-127">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="053d7-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="053d7-128">Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="053d7-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="053d7-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="053d7-129">Parent Elements</span></span>  
  
|<span data-ttu-id="053d7-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="053d7-130">Element</span></span>|<span data-ttu-id="053d7-131">Описание</span><span class="sxs-lookup"><span data-stu-id="053d7-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="053d7-132">привязка</span><span class="sxs-lookup"><span data-stu-id="053d7-132">binding</span></span>|<span data-ttu-id="053d7-133">Элемент привязки для [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="053d7-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="053d7-134">См. также</span><span class="sxs-lookup"><span data-stu-id="053d7-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="053d7-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="053d7-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="053d7-136">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="053d7-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="053d7-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="053d7-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="053d7-138">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="053d7-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="053d7-139">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="053d7-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="053d7-140">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="053d7-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
