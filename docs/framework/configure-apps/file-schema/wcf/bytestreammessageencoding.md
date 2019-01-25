---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 92ae3dc10e0ae734a3113e22f175f4d010ca55b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541863"
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="a71b0-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="a71b0-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="a71b0-103">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="a71b0-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="a71b0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a71b0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a71b0-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a71b0-105">\<bindings></span></span>  
<span data-ttu-id="a71b0-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a71b0-106">\<customBinding></span></span>  
<span data-ttu-id="a71b0-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a71b0-107">\<binding></span></span>  
<span data-ttu-id="a71b0-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="a71b0-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71b0-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a71b0-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a71b0-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a71b0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a71b0-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a71b0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a71b0-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a71b0-112">Attributes</span></span>  
  
|<span data-ttu-id="a71b0-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a71b0-113">Attribute</span></span>|<span data-ttu-id="a71b0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a71b0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a71b0-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="a71b0-115">messageVersion</span></span>|<span data-ttu-id="a71b0-116">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="a71b0-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="a71b0-117">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="a71b0-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="a71b0-118">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="a71b0-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="a71b0-119">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="a71b0-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a71b0-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a71b0-120">Child Elements</span></span>  
  
|<span data-ttu-id="a71b0-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a71b0-121">Element</span></span>|<span data-ttu-id="a71b0-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="a71b0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a71b0-123">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="a71b0-123">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="a71b0-124">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="a71b0-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a71b0-125">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a71b0-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a71b0-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a71b0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a71b0-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="a71b0-127">Element</span></span>|<span data-ttu-id="a71b0-128">Описание</span><span class="sxs-lookup"><span data-stu-id="a71b0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a71b0-129">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a71b0-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a71b0-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="a71b0-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a71b0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a71b0-131">See also</span></span>
- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="a71b0-132">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="a71b0-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="a71b0-133">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="a71b0-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="a71b0-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="a71b0-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a71b0-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="a71b0-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a71b0-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="a71b0-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a71b0-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a71b0-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
