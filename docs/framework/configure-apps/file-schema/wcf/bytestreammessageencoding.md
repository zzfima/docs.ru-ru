---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: b11f472c0e33003e50be4b45bb49196c64ecb70d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919719"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="836f0-101">\<Битестреаммессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="836f0-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="836f0-102">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="836f0-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="836f0-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="836f0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="836f0-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="836f0-104">\<bindings></span></span>  
<span data-ttu-id="836f0-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="836f0-105">\<customBinding></span></span>  
<span data-ttu-id="836f0-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="836f0-106">\<binding></span></span>  
<span data-ttu-id="836f0-107">\<Бинаримессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="836f0-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836f0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="836f0-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="836f0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="836f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="836f0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="836f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="836f0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="836f0-111">Attributes</span></span>  
  
|<span data-ttu-id="836f0-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="836f0-112">Attribute</span></span>|<span data-ttu-id="836f0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="836f0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="836f0-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="836f0-114">messageVersion</span></span>|<span data-ttu-id="836f0-115">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="836f0-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="836f0-116">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="836f0-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="836f0-117">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="836f0-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="836f0-118">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="836f0-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="836f0-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="836f0-119">Child Elements</span></span>  
  
|<span data-ttu-id="836f0-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="836f0-120">Element</span></span>|<span data-ttu-id="836f0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="836f0-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="836f0-122">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="836f0-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="836f0-123">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="836f0-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="836f0-124">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="836f0-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="836f0-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="836f0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="836f0-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="836f0-126">Element</span></span>|<span data-ttu-id="836f0-127">Описание</span><span class="sxs-lookup"><span data-stu-id="836f0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="836f0-128">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="836f0-128">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="836f0-129">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="836f0-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="836f0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="836f0-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="836f0-131">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="836f0-131">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="836f0-132">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="836f0-132">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="836f0-133">Привязки</span><span class="sxs-lookup"><span data-stu-id="836f0-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="836f0-134">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="836f0-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="836f0-135">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="836f0-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="836f0-136">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="836f0-136">\<customBinding></span></span>](custombinding.md)
