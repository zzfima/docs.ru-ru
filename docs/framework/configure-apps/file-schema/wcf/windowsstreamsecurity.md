---
title: '&lt;windowsstreamsecurity инициирует&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a089a6fb61e8f7fac4116b2280a5c2fe0b703f94
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="76e7d-102">&lt;windowsstreamsecurity инициирует&gt;</span><span class="sxs-lookup"><span data-stu-id="76e7d-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="76e7d-103">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="76e7d-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="76e7d-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="76e7d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="76e7d-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="76e7d-105">\<bindings></span></span>  
<span data-ttu-id="76e7d-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="76e7d-106">\<customBinding></span></span>  
<span data-ttu-id="76e7d-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="76e7d-107">\<binding></span></span>  
<span data-ttu-id="76e7d-108">\<windowsstreamsecurity инициирует ></span><span class="sxs-lookup"><span data-stu-id="76e7d-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e7d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76e7d-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76e7d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76e7d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="76e7d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76e7d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76e7d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76e7d-112">Attributes</span></span>  
  
|<span data-ttu-id="76e7d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="76e7d-113">Attribute</span></span>|<span data-ttu-id="76e7d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="76e7d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76e7d-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="76e7d-115">protectionLevel</span></span>|<span data-ttu-id="76e7d-116">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="76e7d-116">Defines message-level security.</span></span> <span data-ttu-id="76e7d-117">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="76e7d-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="76e7d-118">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="76e7d-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="76e7d-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="76e7d-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="76e7d-120">— None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="76e7d-120">-   None: No protection.</span></span><br /><span data-ttu-id="76e7d-121">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="76e7d-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="76e7d-122">-EncryptAndSign: Сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="76e7d-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="76e7d-123">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="76e7d-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="76e7d-124">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="76e7d-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76e7d-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76e7d-125">Child Elements</span></span>  
 <span data-ttu-id="76e7d-126">Нет</span><span class="sxs-lookup"><span data-stu-id="76e7d-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76e7d-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76e7d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="76e7d-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="76e7d-128">Element</span></span>|<span data-ttu-id="76e7d-129">Описание</span><span class="sxs-lookup"><span data-stu-id="76e7d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76e7d-130">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="76e7d-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="76e7d-131">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="76e7d-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76e7d-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="76e7d-132">Remarks</span></span>  
 <span data-ttu-id="76e7d-133">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="76e7d-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="76e7d-134">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="76e7d-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="76e7d-135">Конфигурация этой безопасности транспорта инкапсулируется данного элемента конфигурации, как и с помощью [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), которые можно настроить и добавить в пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="76e7d-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e7d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="76e7d-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="76e7d-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="76e7d-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="76e7d-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="76e7d-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="76e7d-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="76e7d-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="76e7d-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="76e7d-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
