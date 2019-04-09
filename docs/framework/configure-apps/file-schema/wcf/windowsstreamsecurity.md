---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113637"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="8faa4-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="8faa4-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="8faa4-102">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="8faa4-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="8faa4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8faa4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8faa4-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8faa4-104">\<bindings></span></span>  
<span data-ttu-id="8faa4-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8faa4-105">\<customBinding></span></span>  
<span data-ttu-id="8faa4-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8faa4-106">\<binding></span></span>  
<span data-ttu-id="8faa4-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="8faa4-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8faa4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8faa4-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8faa4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8faa4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8faa4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8faa4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8faa4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8faa4-111">Attributes</span></span>  
  
|<span data-ttu-id="8faa4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8faa4-112">Attribute</span></span>|<span data-ttu-id="8faa4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8faa4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8faa4-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="8faa4-114">protectionLevel</span></span>|<span data-ttu-id="8faa4-115">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="8faa4-115">Defines message-level security.</span></span> <span data-ttu-id="8faa4-116">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="8faa4-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="8faa4-117">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="8faa4-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="8faa4-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8faa4-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8faa4-119">-None: Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="8faa4-119">-   None: No protection.</span></span><br /><span data-ttu-id="8faa4-120">-Входа: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="8faa4-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="8faa4-121">-EncryptAndSign: Сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="8faa4-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="8faa4-122">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="8faa4-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="8faa4-123">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="8faa4-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8faa4-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8faa4-124">Child Elements</span></span>  
 <span data-ttu-id="8faa4-125">Нет</span><span class="sxs-lookup"><span data-stu-id="8faa4-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8faa4-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8faa4-126">Parent Elements</span></span>  
  
|<span data-ttu-id="8faa4-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="8faa4-127">Element</span></span>|<span data-ttu-id="8faa4-128">Описание</span><span class="sxs-lookup"><span data-stu-id="8faa4-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8faa4-129">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8faa4-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8faa4-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="8faa4-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8faa4-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8faa4-131">Remarks</span></span>  
 <span data-ttu-id="8faa4-132">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="8faa4-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="8faa4-133">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="8faa4-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="8faa4-134">Конфигурация этой безопасности транспорта инкапсулируется этот элемент конфигурации, как и с помощью [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), который можно настроить и добавить в пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="8faa4-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8faa4-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8faa4-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="8faa4-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="8faa4-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8faa4-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8faa4-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8faa4-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8faa4-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8faa4-139">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8faa4-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
