---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: cddd9f0c1dda982c1795500723c21546bd58c92b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399101"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="ed151-101">\<Windowsstreamsecurity инициирует обновление ></span><span class="sxs-lookup"><span data-stu-id="ed151-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="ed151-102">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ed151-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="ed151-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ed151-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ed151-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ed151-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ed151-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ed151-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ed151-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="ed151-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="ed151-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="ed151-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ed151-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Windowsstreamsecurity инициирует обновление >**</span><span class="sxs-lookup"><span data-stu-id="ed151-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed151-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed151-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed151-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed151-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ed151-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ed151-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed151-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed151-112">Attributes</span></span>  
  
|<span data-ttu-id="ed151-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ed151-113">Attribute</span></span>|<span data-ttu-id="ed151-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ed151-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed151-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="ed151-115">protectionLevel</span></span>|<span data-ttu-id="ed151-116">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed151-116">Defines message-level security.</span></span> <span data-ttu-id="ed151-117">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="ed151-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="ed151-118">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="ed151-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="ed151-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ed151-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ed151-120">None Нет защиты.</span><span class="sxs-lookup"><span data-stu-id="ed151-120">-   None: No protection.</span></span><br /><span data-ttu-id="ed151-121">Писать Сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="ed151-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ed151-122">EncryptAndSign Сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="ed151-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="ed151-123">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="ed151-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="ed151-124">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="ed151-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed151-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed151-125">Child Elements</span></span>  
 <span data-ttu-id="ed151-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ed151-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed151-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed151-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ed151-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed151-128">Element</span></span>|<span data-ttu-id="ed151-129">Описание</span><span class="sxs-lookup"><span data-stu-id="ed151-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed151-130">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ed151-130">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ed151-131">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ed151-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed151-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed151-132">Remarks</span></span>  
 <span data-ttu-id="ed151-133">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="ed151-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="ed151-134">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed151-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="ed151-135">Конфигурация этой защиты транспорта инкапсулирована этим элементом конфигурации, а также [ \<раздел sslstreamsecurity >](sslstreamsecurity.md), который можно настроить и добавить в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="ed151-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed151-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ed151-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="ed151-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="ed151-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ed151-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="ed151-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ed151-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="ed151-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ed151-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ed151-140">\<customBinding></span></span>](custombinding.md)
