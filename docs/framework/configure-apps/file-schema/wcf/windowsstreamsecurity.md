---
title: "&lt;windowsstreamsecurity инициирует&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3ebbb7749a5ca24072e62bb482ee33abadcfb8b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="3770e-102">&lt;windowsstreamsecurity инициирует&gt;</span><span class="sxs-lookup"><span data-stu-id="3770e-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="3770e-103">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3770e-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="3770e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3770e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3770e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3770e-105">\<bindings></span></span>  
<span data-ttu-id="3770e-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3770e-106">\<customBinding></span></span>  
<span data-ttu-id="3770e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3770e-107">\<binding></span></span>  
<span data-ttu-id="3770e-108">\<windowsstreamsecurity инициирует ></span><span class="sxs-lookup"><span data-stu-id="3770e-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3770e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3770e-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3770e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3770e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3770e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3770e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3770e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3770e-112">Attributes</span></span>  
  
|<span data-ttu-id="3770e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3770e-113">Attribute</span></span>|<span data-ttu-id="3770e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3770e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3770e-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="3770e-115">protectionLevel</span></span>|<span data-ttu-id="3770e-116">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="3770e-116">Defines message-level security.</span></span> <span data-ttu-id="3770e-117">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="3770e-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="3770e-118">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="3770e-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="3770e-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3770e-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3770e-120">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="3770e-120">-   None: No protection.</span></span><br /><span data-ttu-id="3770e-121">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="3770e-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="3770e-122">-EncryptAndSign: Сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="3770e-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="3770e-123">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="3770e-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="3770e-124">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="3770e-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3770e-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3770e-125">Child Elements</span></span>  
 <span data-ttu-id="3770e-126">Нет</span><span class="sxs-lookup"><span data-stu-id="3770e-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3770e-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3770e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3770e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="3770e-128">Element</span></span>|<span data-ttu-id="3770e-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="3770e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3770e-130">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3770e-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3770e-131">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3770e-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3770e-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="3770e-132">Remarks</span></span>  
 <span data-ttu-id="3770e-133">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="3770e-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="3770e-134">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="3770e-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="3770e-135">Конфигурация этой безопасности транспорта инкапсулируется данного элемента конфигурации, как и с помощью [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), которые можно настроить и добавить в пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="3770e-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3770e-136">См. также</span><span class="sxs-lookup"><span data-stu-id="3770e-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="3770e-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="3770e-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3770e-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="3770e-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3770e-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="3770e-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3770e-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3770e-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
