---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 4b031bfb0d0979dc99df13c104a712d6dd771e8a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44225192"
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="11848-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="11848-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="11848-103">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="11848-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="11848-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="11848-104">\<system.serviceModel></span></span>  
<span data-ttu-id="11848-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="11848-105">\<bindings></span></span>  
<span data-ttu-id="11848-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="11848-106">\<customBinding></span></span>  
<span data-ttu-id="11848-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="11848-107">\<binding></span></span>  
<span data-ttu-id="11848-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="11848-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11848-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11848-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11848-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="11848-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11848-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="11848-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11848-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11848-112">Attributes</span></span>  
  
|<span data-ttu-id="11848-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="11848-113">Attribute</span></span>|<span data-ttu-id="11848-114">Описание</span><span class="sxs-lookup"><span data-stu-id="11848-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11848-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="11848-115">messageVersion</span></span>|<span data-ttu-id="11848-116">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="11848-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="11848-117">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="11848-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="11848-118">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="11848-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="11848-119">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="11848-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11848-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11848-120">Child Elements</span></span>  
  
|<span data-ttu-id="11848-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="11848-121">Element</span></span>|<span data-ttu-id="11848-122">Описание</span><span class="sxs-lookup"><span data-stu-id="11848-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11848-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="11848-123">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="11848-124">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="11848-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="11848-125">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="11848-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11848-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="11848-126">Parent Elements</span></span>  
  
|<span data-ttu-id="11848-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="11848-127">Element</span></span>|<span data-ttu-id="11848-128">Описание</span><span class="sxs-lookup"><span data-stu-id="11848-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11848-129">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="11848-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="11848-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="11848-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11848-131">См. также</span><span class="sxs-lookup"><span data-stu-id="11848-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="11848-132">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="11848-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="11848-133">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="11848-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="11848-134">Привязки</span><span class="sxs-lookup"><span data-stu-id="11848-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="11848-135">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="11848-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="11848-136">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="11848-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="11848-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="11848-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
