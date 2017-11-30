---
title: "&lt;transport&gt; для &lt;netNamedPipeBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 00f4ddfd218e8797aa2089a21081ee711be316d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="c0980-102">&lt;transport&gt; для &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c0980-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="c0980-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="c0980-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="c0980-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c0980-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c0980-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="c0980-105">\<bindings></span></span>  
<span data-ttu-id="c0980-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="c0980-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="c0980-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c0980-107">\<binding></span></span>  
<span data-ttu-id="c0980-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c0980-108">\<security></span></span>  
<span data-ttu-id="c0980-109">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="c0980-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0980-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0980-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0980-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0980-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c0980-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c0980-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0980-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0980-113">Attributes</span></span>  
  
|<span data-ttu-id="c0980-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c0980-114">Attribute</span></span>|<span data-ttu-id="c0980-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c0980-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0980-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="c0980-116">protectionLevel</span></span>|<span data-ttu-id="c0980-117">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="c0980-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="c0980-118">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="c0980-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="c0980-119">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="c0980-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="c0980-120">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c0980-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c0980-121">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="c0980-121">-   None: No protection.</span></span><br /><span data-ttu-id="c0980-122">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="c0980-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c0980-123">-EncryptAndSign: Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="c0980-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c0980-124">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="c0980-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0980-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0980-125">Child Elements</span></span>  
 <span data-ttu-id="c0980-126">Нет</span><span class="sxs-lookup"><span data-stu-id="c0980-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0980-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0980-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c0980-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0980-128">Element</span></span>|<span data-ttu-id="c0980-129">Описание</span><span class="sxs-lookup"><span data-stu-id="c0980-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0980-130">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c0980-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="c0980-131">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="c0980-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0980-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c0980-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="c0980-133">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c0980-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c0980-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="c0980-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c0980-135">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="c0980-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c0980-136">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="c0980-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="c0980-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c0980-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
