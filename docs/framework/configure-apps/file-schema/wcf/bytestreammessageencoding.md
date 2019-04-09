---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109906"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="38488-101">\<byteStreamMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="38488-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="38488-102">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="38488-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="38488-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="38488-103">\<system.serviceModel></span></span>  
<span data-ttu-id="38488-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="38488-104">\<bindings></span></span>  
<span data-ttu-id="38488-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="38488-105">\<customBinding></span></span>  
<span data-ttu-id="38488-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="38488-106">\<binding></span></span>  
<span data-ttu-id="38488-107">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="38488-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38488-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38488-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38488-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38488-109">Attributes and Elements</span></span>  
 <span data-ttu-id="38488-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38488-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38488-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38488-111">Attributes</span></span>  
  
|<span data-ttu-id="38488-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="38488-112">Attribute</span></span>|<span data-ttu-id="38488-113">Описание</span><span class="sxs-lookup"><span data-stu-id="38488-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38488-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="38488-114">messageVersion</span></span>|<span data-ttu-id="38488-115">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="38488-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="38488-116">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="38488-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="38488-117">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="38488-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="38488-118">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="38488-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38488-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38488-119">Child Elements</span></span>  
  
|<span data-ttu-id="38488-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="38488-120">Element</span></span>|<span data-ttu-id="38488-121">Описание</span><span class="sxs-lookup"><span data-stu-id="38488-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38488-122">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="38488-122">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="38488-123">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="38488-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="38488-124">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="38488-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38488-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38488-125">Parent Elements</span></span>  
  
|<span data-ttu-id="38488-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="38488-126">Element</span></span>|<span data-ttu-id="38488-127">Описание</span><span class="sxs-lookup"><span data-stu-id="38488-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38488-128">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="38488-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="38488-129">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="38488-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38488-130">См. также</span><span class="sxs-lookup"><span data-stu-id="38488-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="38488-131">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="38488-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="38488-132">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="38488-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="38488-133">Привязки</span><span class="sxs-lookup"><span data-stu-id="38488-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="38488-134">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="38488-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="38488-135">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="38488-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="38488-136">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="38488-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
