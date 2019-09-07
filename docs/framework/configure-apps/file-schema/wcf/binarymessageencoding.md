---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: feefd7fe73363b5fe1ec5658c5dc339c3d6bac57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398212"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="5c491-101">\<Бинаримессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="5c491-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="5c491-102">Определяет кодировщик двоичных сообщений, кодирующий сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="5c491-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
<span data-ttu-id="5c491-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c491-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c491-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5c491-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5c491-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="5c491-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5c491-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="5c491-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="5c491-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="5c491-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5c491-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Бинаримессажеенкодинг >**</span><span class="sxs-lookup"><span data-stu-id="5c491-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c491-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c491-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c491-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c491-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c491-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5c491-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c491-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c491-112">Attributes</span></span>  
  
|<span data-ttu-id="5c491-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5c491-113">Attribute</span></span>|<span data-ttu-id="5c491-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5c491-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c491-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="5c491-115">maxReadPoolSize</span></span>|<span data-ttu-id="5c491-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="5c491-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="5c491-117">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="5c491-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5c491-118">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="5c491-118">The default is 64.</span></span>|  
|<span data-ttu-id="5c491-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="5c491-119">maxSessionSize</span></span>|<span data-ttu-id="5c491-120">Положительное целое число, задающее размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="5c491-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="5c491-121">Буфер большего размера повышает скорость кодирования за счет размера рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="5c491-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="5c491-122">Значение по умолчанию — 2048.</span><span class="sxs-lookup"><span data-stu-id="5c491-122">The default is 2048.</span></span>|  
|<span data-ttu-id="5c491-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="5c491-123">maxWritePoolSize</span></span>|<span data-ttu-id="5c491-124">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="5c491-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="5c491-125">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="5c491-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5c491-126">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="5c491-126">The default is 16.</span></span>|  
|<span data-ttu-id="5c491-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="5c491-127">messageVersion</span></span>|<span data-ttu-id="5c491-128">Определяет используемые или ожидаемые версии сообщения SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="5c491-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c491-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c491-129">Child Elements</span></span>  
  
|<span data-ttu-id="5c491-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c491-130">Element</span></span>|<span data-ttu-id="5c491-131">Описание</span><span class="sxs-lookup"><span data-stu-id="5c491-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c491-132">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5c491-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="5c491-133">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="5c491-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5c491-134">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="5c491-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c491-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c491-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5c491-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c491-136">Element</span></span>|<span data-ttu-id="5c491-137">Описание</span><span class="sxs-lookup"><span data-stu-id="5c491-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c491-138">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5c491-138">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="5c491-139">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="5c491-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c491-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c491-140">Remarks</span></span>  
 <span data-ttu-id="5c491-141">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="5c491-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="5c491-142">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="5c491-142">Decoding is the reverse process.</span></span> <span data-ttu-id="5c491-143">Windows Communication Foundation (WCF) включает три типа кодировки для сообщений SOAP: Text, binary и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="5c491-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="5c491-144">Элемент `binaryMessageEncoding` указывает двоичный формат .NET для XML и содержит параметры, задающие кодировку символов и версию SOAP и WS-Addressing для использования.</span><span class="sxs-lookup"><span data-stu-id="5c491-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="5c491-145">Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="5c491-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="5c491-146">Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-\*.</span><span class="sxs-lookup"><span data-stu-id="5c491-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c491-147">Пример</span><span class="sxs-lookup"><span data-stu-id="5c491-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5c491-148">См. также</span><span class="sxs-lookup"><span data-stu-id="5c491-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="5c491-149">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="5c491-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="5c491-150">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="5c491-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="5c491-151">Привязки</span><span class="sxs-lookup"><span data-stu-id="5c491-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5c491-152">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="5c491-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5c491-153">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="5c491-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5c491-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5c491-154">\<customBinding></span></span>](custombinding.md)
