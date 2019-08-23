---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 0f1dfd523e593c82727354db7ce39ffc992bdfb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932809"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="29cee-101">\<Windowsstreamsecurity инициирует обновление ></span><span class="sxs-lookup"><span data-stu-id="29cee-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="29cee-102">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="29cee-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="29cee-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="29cee-103">\<system.serviceModel></span></span>  
<span data-ttu-id="29cee-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="29cee-104">\<bindings></span></span>  
<span data-ttu-id="29cee-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="29cee-105">\<customBinding></span></span>  
<span data-ttu-id="29cee-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="29cee-106">\<binding></span></span>  
<span data-ttu-id="29cee-107">\<Windowsstreamsecurity инициирует обновление ></span><span class="sxs-lookup"><span data-stu-id="29cee-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29cee-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29cee-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29cee-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29cee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="29cee-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29cee-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29cee-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29cee-111">Attributes</span></span>  
  
|<span data-ttu-id="29cee-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="29cee-112">Attribute</span></span>|<span data-ttu-id="29cee-113">Описание</span><span class="sxs-lookup"><span data-stu-id="29cee-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29cee-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="29cee-114">protectionLevel</span></span>|<span data-ttu-id="29cee-115">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="29cee-115">Defines message-level security.</span></span> <span data-ttu-id="29cee-116">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="29cee-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="29cee-117">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="29cee-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="29cee-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="29cee-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29cee-119">None Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="29cee-119">-   None: No protection.</span></span><br /><span data-ttu-id="29cee-120">Писать Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="29cee-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="29cee-121">EncryptAndSign Сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="29cee-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="29cee-122">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="29cee-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="29cee-123">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="29cee-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29cee-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29cee-124">Child Elements</span></span>  
 <span data-ttu-id="29cee-125">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="29cee-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29cee-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29cee-126">Parent Elements</span></span>  
  
|<span data-ttu-id="29cee-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="29cee-127">Element</span></span>|<span data-ttu-id="29cee-128">Описание</span><span class="sxs-lookup"><span data-stu-id="29cee-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29cee-129">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="29cee-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="29cee-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="29cee-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29cee-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="29cee-131">Remarks</span></span>  
 <span data-ttu-id="29cee-132">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="29cee-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="29cee-133">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="29cee-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="29cee-134">Конфигурация этой защиты транспорта инкапсулирована этим элементом конфигурации, а также [ \<раздел sslstreamsecurity >](sslstreamsecurity.md), который можно настроить и добавить в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="29cee-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29cee-135">См. также</span><span class="sxs-lookup"><span data-stu-id="29cee-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="29cee-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="29cee-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="29cee-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="29cee-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="29cee-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="29cee-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="29cee-139">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="29cee-139">\<customBinding></span></span>](custombinding.md)
