---
title: '&lt;windowsstreamsecurity инициирует&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: e117c30ba2583158ee21fd11ff4a38b094c18fd9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197643"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="d7152-102">&lt;windowsstreamsecurity инициирует&gt;</span><span class="sxs-lookup"><span data-stu-id="d7152-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="d7152-103">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d7152-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="d7152-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d7152-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d7152-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d7152-105">\<bindings></span></span>  
<span data-ttu-id="d7152-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d7152-106">\<customBinding></span></span>  
<span data-ttu-id="d7152-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d7152-107">\<binding></span></span>  
<span data-ttu-id="d7152-108">\<windowsstreamsecurity инициирует ></span><span class="sxs-lookup"><span data-stu-id="d7152-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7152-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7152-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7152-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d7152-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d7152-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d7152-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7152-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d7152-112">Attributes</span></span>  
  
|<span data-ttu-id="d7152-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d7152-113">Attribute</span></span>|<span data-ttu-id="d7152-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d7152-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7152-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="d7152-115">protectionLevel</span></span>|<span data-ttu-id="d7152-116">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="d7152-116">Defines message-level security.</span></span> <span data-ttu-id="d7152-117">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="d7152-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="d7152-118">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="d7152-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="d7152-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d7152-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d7152-120">-None: Без защиты.</span><span class="sxs-lookup"><span data-stu-id="d7152-120">-   None: No protection.</span></span><br /><span data-ttu-id="d7152-121">-Sign: Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="d7152-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="d7152-122">-EncryptAndSign: Сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="d7152-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="d7152-123">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="d7152-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="d7152-124">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="d7152-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7152-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d7152-125">Child Elements</span></span>  
 <span data-ttu-id="d7152-126">Нет</span><span class="sxs-lookup"><span data-stu-id="d7152-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7152-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d7152-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d7152-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d7152-128">Element</span></span>|<span data-ttu-id="d7152-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d7152-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7152-130">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d7152-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d7152-131">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d7152-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7152-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7152-132">Remarks</span></span>  
 <span data-ttu-id="d7152-133">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="d7152-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="d7152-134">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d7152-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="d7152-135">Конфигурация этой безопасности транспорта инкапсулируется этот элемент конфигурации, как и с помощью [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), который можно настроить и добавить в пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="d7152-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7152-136">См. также</span><span class="sxs-lookup"><span data-stu-id="d7152-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="d7152-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="d7152-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d7152-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="d7152-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d7152-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="d7152-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d7152-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d7152-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
