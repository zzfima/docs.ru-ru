---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 165bf4cd1c0c5c1a6adae91650d38984bc47ef6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="56919-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="56919-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="56919-103">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="56919-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="56919-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="56919-104">\<system.serviceModel></span></span>  
<span data-ttu-id="56919-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="56919-105">\<bindings></span></span>  
<span data-ttu-id="56919-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="56919-106">\<customBinding></span></span>  
<span data-ttu-id="56919-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="56919-107">\<binding></span></span>  
<span data-ttu-id="56919-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="56919-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56919-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56919-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56919-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56919-110">Attributes and Elements</span></span>  
 <span data-ttu-id="56919-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56919-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56919-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56919-112">Attributes</span></span>  
  
|<span data-ttu-id="56919-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="56919-113">Attribute</span></span>|<span data-ttu-id="56919-114">Описание</span><span class="sxs-lookup"><span data-stu-id="56919-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56919-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="56919-115">messageVersion</span></span>|<span data-ttu-id="56919-116">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="56919-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="56919-117">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="56919-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="56919-118">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="56919-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="56919-119">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="56919-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56919-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56919-120">Child Elements</span></span>  
  
|<span data-ttu-id="56919-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="56919-121">Element</span></span>|<span data-ttu-id="56919-122">Описание</span><span class="sxs-lookup"><span data-stu-id="56919-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56919-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="56919-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="56919-124">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="56919-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="56919-125">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="56919-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56919-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56919-126">Parent Elements</span></span>  
  
|<span data-ttu-id="56919-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="56919-127">Element</span></span>|<span data-ttu-id="56919-128">Описание</span><span class="sxs-lookup"><span data-stu-id="56919-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56919-129">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="56919-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="56919-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="56919-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56919-131">См. также</span><span class="sxs-lookup"><span data-stu-id="56919-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="56919-132">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="56919-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="56919-133">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="56919-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="56919-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="56919-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="56919-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="56919-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="56919-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="56919-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="56919-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="56919-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
