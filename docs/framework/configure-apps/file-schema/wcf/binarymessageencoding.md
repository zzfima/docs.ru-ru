---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: e02ed6ef79fcf52bbe9c33bd9b36a14113e19d1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228384"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="6af6e-101">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="6af6e-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="6af6e-102">Определяет кодировщик двоичных сообщений, кодирующий сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="6af6e-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="6af6e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6af6e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="6af6e-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="6af6e-104">\<bindings></span></span>  
<span data-ttu-id="6af6e-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6af6e-105">\<customBinding></span></span>  
<span data-ttu-id="6af6e-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6af6e-106">\<binding></span></span>  
<span data-ttu-id="6af6e-107">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="6af6e-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af6e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6af6e-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6af6e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6af6e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6af6e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6af6e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6af6e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6af6e-111">Attributes</span></span>  
  
|<span data-ttu-id="6af6e-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6af6e-112">Attribute</span></span>|<span data-ttu-id="6af6e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6af6e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6af6e-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="6af6e-114">maxReadPoolSize</span></span>|<span data-ttu-id="6af6e-115">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="6af6e-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="6af6e-116">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="6af6e-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="6af6e-117">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="6af6e-117">The default is 64.</span></span>|  
|<span data-ttu-id="6af6e-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="6af6e-118">maxSessionSize</span></span>|<span data-ttu-id="6af6e-119">Положительное целое число, задающее размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="6af6e-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="6af6e-120">Буфер большего размера повышает скорость кодирования за счет размера рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="6af6e-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="6af6e-121">Значение по умолчанию — 2048.</span><span class="sxs-lookup"><span data-stu-id="6af6e-121">The default is 2048.</span></span>|  
|<span data-ttu-id="6af6e-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="6af6e-122">maxWritePoolSize</span></span>|<span data-ttu-id="6af6e-123">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="6af6e-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="6af6e-124">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="6af6e-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="6af6e-125">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="6af6e-125">The default is 16.</span></span>|  
|<span data-ttu-id="6af6e-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="6af6e-126">messageVersion</span></span>|<span data-ttu-id="6af6e-127">Определяет используемые или ожидаемые версии сообщения SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="6af6e-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6af6e-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6af6e-128">Child Elements</span></span>  
  
|<span data-ttu-id="6af6e-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="6af6e-129">Element</span></span>|<span data-ttu-id="6af6e-130">Описание</span><span class="sxs-lookup"><span data-stu-id="6af6e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af6e-131">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="6af6e-131">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="6af6e-132">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="6af6e-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="6af6e-133">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="6af6e-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6af6e-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6af6e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="6af6e-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="6af6e-135">Element</span></span>|<span data-ttu-id="6af6e-136">Описание</span><span class="sxs-lookup"><span data-stu-id="6af6e-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af6e-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="6af6e-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6af6e-138">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="6af6e-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6af6e-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="6af6e-139">Remarks</span></span>  
 <span data-ttu-id="6af6e-140">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="6af6e-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="6af6e-141">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="6af6e-141">Decoding is the reverse process.</span></span> <span data-ttu-id="6af6e-142">Windows Communication Foundation (WCF) включает в себя три типа кодирования для сообщений SOAP: Текст, двоичное кодирование и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="6af6e-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="6af6e-143">Элемент `binaryMessageEncoding` указывает двоичный формат .NET для XML и содержит параметры, задающие кодировку символов и версию SOAP и WS-Addressing для использования.</span><span class="sxs-lookup"><span data-stu-id="6af6e-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="6af6e-144">Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="6af6e-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="6af6e-145">Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-\*.</span><span class="sxs-lookup"><span data-stu-id="6af6e-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6af6e-146">Пример</span><span class="sxs-lookup"><span data-stu-id="6af6e-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="6af6e-147">См. также</span><span class="sxs-lookup"><span data-stu-id="6af6e-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="6af6e-148">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="6af6e-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="6af6e-149">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="6af6e-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="6af6e-150">Привязки</span><span class="sxs-lookup"><span data-stu-id="6af6e-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6af6e-151">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="6af6e-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6af6e-152">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="6af6e-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6af6e-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6af6e-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
