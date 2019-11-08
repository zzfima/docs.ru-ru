---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735893"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="ca69d-101">\<Windowsstreamsecurity инициирует обновление ></span><span class="sxs-lookup"><span data-stu-id="ca69d-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="ca69d-102">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ca69d-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="ca69d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca69d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ca69d-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ca69d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ca69d-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="ca69d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="ca69d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="ca69d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="ca69d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="ca69d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ca69d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsstreamsecurity инициирует обновление >**</span><span class="sxs-lookup"><span data-stu-id="ca69d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca69d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca69d-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca69d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ca69d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca69d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ca69d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca69d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ca69d-112">Attributes</span></span>  
  
|<span data-ttu-id="ca69d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ca69d-113">Attribute</span></span>|<span data-ttu-id="ca69d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ca69d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca69d-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="ca69d-115">protectionLevel</span></span>|<span data-ttu-id="ca69d-116">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="ca69d-116">Defines message-level security.</span></span> <span data-ttu-id="ca69d-117">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="ca69d-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="ca69d-118">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="ca69d-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="ca69d-119">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ca69d-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ca69d-120">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ca69d-120">-   None: No protection.</span></span><br /><span data-ttu-id="ca69d-121">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="ca69d-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ca69d-122">-EncryptAndSign: сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="ca69d-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="ca69d-123">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="ca69d-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="ca69d-124">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="ca69d-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca69d-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ca69d-125">Child Elements</span></span>  
 <span data-ttu-id="ca69d-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ca69d-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca69d-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ca69d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ca69d-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca69d-128">Element</span></span>|<span data-ttu-id="ca69d-129">Описание</span><span class="sxs-lookup"><span data-stu-id="ca69d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca69d-130">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="ca69d-130">\<binding></span></span>](bindings.md)|<span data-ttu-id="ca69d-131">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ca69d-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca69d-132">Заметки</span><span class="sxs-lookup"><span data-stu-id="ca69d-132">Remarks</span></span>  
 <span data-ttu-id="ca69d-133">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="ca69d-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="ca69d-134">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca69d-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="ca69d-135">Конфигурация этой защиты транспорта инкапсулирована этим элементом конфигурации, а также [\<раздел sslstreamsecurity >](sslstreamsecurity.md), который можно настроить и добавить в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="ca69d-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca69d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ca69d-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="ca69d-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="ca69d-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ca69d-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="ca69d-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ca69d-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="ca69d-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ca69d-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ca69d-140">\<customBinding></span></span>](custombinding.md)
