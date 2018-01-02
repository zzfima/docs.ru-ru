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
ms.workload: dotnet
ms.openlocfilehash: 1996a33666ac6b92f1b7bca8c2e2e0ef51456dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="d86b8-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="d86b8-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="d86b8-103">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="d86b8-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="d86b8-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d86b8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d86b8-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d86b8-105">\<bindings></span></span>  
<span data-ttu-id="d86b8-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d86b8-106">\<customBinding></span></span>  
<span data-ttu-id="d86b8-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d86b8-107">\<binding></span></span>  
<span data-ttu-id="d86b8-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="d86b8-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d86b8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d86b8-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d86b8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d86b8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d86b8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d86b8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d86b8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d86b8-112">Attributes</span></span>  
  
|<span data-ttu-id="d86b8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d86b8-113">Attribute</span></span>|<span data-ttu-id="d86b8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d86b8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d86b8-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d86b8-115">messageVersion</span></span>|<span data-ttu-id="d86b8-116">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="d86b8-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d86b8-117">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="d86b8-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d86b8-118">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="d86b8-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d86b8-119">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d86b8-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d86b8-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d86b8-120">Child Elements</span></span>  
  
|<span data-ttu-id="d86b8-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d86b8-121">Element</span></span>|<span data-ttu-id="d86b8-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="d86b8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d86b8-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="d86b8-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="d86b8-124">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="d86b8-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d86b8-125">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d86b8-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d86b8-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d86b8-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d86b8-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="d86b8-127">Element</span></span>|<span data-ttu-id="d86b8-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="d86b8-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d86b8-129">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d86b8-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d86b8-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d86b8-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d86b8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d86b8-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="d86b8-132">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="d86b8-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="d86b8-133">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="d86b8-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="d86b8-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="d86b8-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d86b8-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="d86b8-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d86b8-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="d86b8-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d86b8-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d86b8-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
