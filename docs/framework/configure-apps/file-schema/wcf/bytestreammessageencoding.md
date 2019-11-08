---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739062"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="4c4d9-101">\<Битестреаммессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="4c4d9-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="4c4d9-102">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="4c4d9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c4d9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c4d9-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4c4d9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4c4d9-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="4c4d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="4c4d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4c4d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4c4d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="4c4d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4c4d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<битестреаммессажеенкодинг >**</span><span class="sxs-lookup"><span data-stu-id="4c4d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c4d9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c4d9-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c4d9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c4d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4c4d9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c4d9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c4d9-112">Attributes</span></span>  
  
|<span data-ttu-id="4c4d9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4c4d9-113">Attribute</span></span>|<span data-ttu-id="4c4d9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4c4d9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c4d9-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4c4d9-115">messageVersion</span></span>|<span data-ttu-id="4c4d9-116">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4c4d9-117">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="4c4d9-118">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="4c4d9-119">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c4d9-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c4d9-120">Child Elements</span></span>  
  
|<span data-ttu-id="4c4d9-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c4d9-121">Element</span></span>|<span data-ttu-id="4c4d9-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4c4d9-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c4d9-123">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4c4d9-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="4c4d9-124">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4c4d9-125">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c4d9-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c4d9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="4c4d9-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c4d9-127">Element</span></span>|<span data-ttu-id="4c4d9-128">Описание</span><span class="sxs-lookup"><span data-stu-id="4c4d9-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c4d9-129">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="4c4d9-129">\<binding></span></span>](bindings.md)|<span data-ttu-id="4c4d9-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="4c4d9-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c4d9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4c4d9-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="4c4d9-132">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="4c4d9-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="4c4d9-133">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="4c4d9-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4c4d9-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="4c4d9-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4c4d9-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4c4d9-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4c4d9-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4c4d9-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4c4d9-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4c4d9-137">\<customBinding></span></span>](custombinding.md)
