---
title: <security> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0996a98438dc344d96d640abced52ac99709adbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936675"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="f62ca-102">\<> безопасности > \<NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="f62ca-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="f62ca-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="f62ca-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="f62ca-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f62ca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f62ca-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f62ca-105">\<bindings></span></span>  
<span data-ttu-id="f62ca-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="f62ca-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="f62ca-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f62ca-107">\<binding></span></span>  
<span data-ttu-id="f62ca-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="f62ca-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f62ca-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f62ca-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f62ca-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f62ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f62ca-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f62ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f62ca-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f62ca-112">Attributes</span></span>  
  
|<span data-ttu-id="f62ca-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f62ca-113">Attribute</span></span>|<span data-ttu-id="f62ca-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f62ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62ca-115">режим</span><span class="sxs-lookup"><span data-stu-id="f62ca-115">mode</span></span>|<span data-ttu-id="f62ca-116">Задает тип системы безопасности, применяемой к этой привязке.</span><span class="sxs-lookup"><span data-stu-id="f62ca-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="f62ca-117">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f62ca-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f62ca-118">None Это отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="f62ca-118">-   None: This disables security.</span></span><br /><span data-ttu-id="f62ca-119">Перемещения Безопасность обеспечивается с помощью базовой безопасности на основе транспорта.</span><span class="sxs-lookup"><span data-stu-id="f62ca-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="f62ca-120">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="f62ca-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="f62ca-121">— Значение по умолчанию — Transport.</span><span class="sxs-lookup"><span data-stu-id="f62ca-121">-   The default value is Transport.</span></span> <span data-ttu-id="f62ca-122">Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f62ca-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f62ca-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f62ca-123">Child Elements</span></span>  
  
|<span data-ttu-id="f62ca-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f62ca-124">Element</span></span>|<span data-ttu-id="f62ca-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f62ca-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f62ca-126">транспорт</span><span class="sxs-lookup"><span data-stu-id="f62ca-126">transport</span></span>|<span data-ttu-id="f62ca-127">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="f62ca-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="f62ca-128">Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f62ca-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f62ca-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f62ca-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f62ca-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="f62ca-130">Element</span></span>|<span data-ttu-id="f62ca-131">Описание</span><span class="sxs-lookup"><span data-stu-id="f62ca-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f62ca-132">привязка</span><span class="sxs-lookup"><span data-stu-id="f62ca-132">binding</span></span>|<span data-ttu-id="f62ca-133">[ Элемент\<Binding > NetNamedPipeBinding](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="f62ca-133">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f62ca-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f62ca-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="f62ca-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f62ca-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f62ca-136">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="f62ca-136">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="f62ca-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="f62ca-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f62ca-138">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f62ca-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f62ca-139">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f62ca-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f62ca-140">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f62ca-140">\<binding></span></span>](../../../misc/binding.md)
