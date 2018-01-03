---
title: '&lt;binaryMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 503c0edf3a21b3fb0f57b5199aa2a1a17df4222d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="09131-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="09131-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="09131-103">Определяет кодировщик двоичных сообщений, кодирующий сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="09131-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="09131-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="09131-104">\<system.serviceModel></span></span>  
<span data-ttu-id="09131-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="09131-105">\<bindings></span></span>  
<span data-ttu-id="09131-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="09131-106">\<customBinding></span></span>  
<span data-ttu-id="09131-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="09131-107">\<binding></span></span>  
<span data-ttu-id="09131-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="09131-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09131-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09131-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"   messageVersion="Soap11Addressing10/Soap12Addressing10" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09131-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09131-110">Attributes and Elements</span></span>  
 <span data-ttu-id="09131-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09131-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09131-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09131-112">Attributes</span></span>  
  
|<span data-ttu-id="09131-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="09131-113">Attribute</span></span>|<span data-ttu-id="09131-114">Описание</span><span class="sxs-lookup"><span data-stu-id="09131-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09131-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="09131-115">maxReadPoolSize</span></span>|<span data-ttu-id="09131-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="09131-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="09131-117">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="09131-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="09131-118">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="09131-118">The default is 64.</span></span>|  
|<span data-ttu-id="09131-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="09131-119">maxSessionSize</span></span>|<span data-ttu-id="09131-120">Положительное целое число, задающее размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="09131-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="09131-121">Буфер большего размера повышает скорость кодирования за счет размера рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="09131-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="09131-122">Значение по умолчанию — 2048.</span><span class="sxs-lookup"><span data-stu-id="09131-122">The default is 2048.</span></span>|  
|<span data-ttu-id="09131-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="09131-123">maxWritePoolSize</span></span>|<span data-ttu-id="09131-124">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="09131-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="09131-125">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="09131-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="09131-126">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="09131-126">The default is 16.</span></span>|  
|<span data-ttu-id="09131-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="09131-127">messageVersion</span></span>|<span data-ttu-id="09131-128">Определяет используемые или ожидаемые версии сообщения SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="09131-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09131-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09131-129">Child Elements</span></span>  
  
|<span data-ttu-id="09131-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="09131-130">Element</span></span>|<span data-ttu-id="09131-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="09131-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09131-132">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="09131-132">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="09131-133">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="09131-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="09131-134">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="09131-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09131-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09131-135">Parent Elements</span></span>  
  
|<span data-ttu-id="09131-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="09131-136">Element</span></span>|<span data-ttu-id="09131-137">Описание:</span><span class="sxs-lookup"><span data-stu-id="09131-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09131-138">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="09131-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="09131-139">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="09131-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09131-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="09131-140">Remarks</span></span>  
 <span data-ttu-id="09131-141">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="09131-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="09131-142">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="09131-142">Decoding is the reverse process.</span></span> <span data-ttu-id="09131-143">В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.</span><span class="sxs-lookup"><span data-stu-id="09131-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="09131-144">Элемент `binaryMessageEncoding` указывает двоичный формат .NET для XML и содержит параметры, задающие кодировку символов и версию SOAP и WS-Addressing для использования.</span><span class="sxs-lookup"><span data-stu-id="09131-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="09131-145">Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="09131-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="09131-146">Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-*.</span><span class="sxs-lookup"><span data-stu-id="09131-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09131-147">Пример</span><span class="sxs-lookup"><span data-stu-id="09131-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="09131-148">См. также</span><span class="sxs-lookup"><span data-stu-id="09131-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="09131-149">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="09131-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="09131-150">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="09131-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="09131-151">Привязки</span><span class="sxs-lookup"><span data-stu-id="09131-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="09131-152">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="09131-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="09131-153">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="09131-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="09131-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="09131-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
