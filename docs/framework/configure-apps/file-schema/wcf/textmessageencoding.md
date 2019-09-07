---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 1494cee0e412bebc6637ad73354f7c91dc636e15
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399431"
---
# <a name="textmessageencoding"></a><span data-ttu-id="2a667-101">\<Текстмессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="2a667-101">\<textMessageEncoding></span></span>
<span data-ttu-id="2a667-102">Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="2a667-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
<span data-ttu-id="2a667-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a667-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2a667-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2a667-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2a667-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2a667-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2a667-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2a667-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="2a667-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="2a667-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2a667-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Текстмессажеенкодинг >**</span><span class="sxs-lookup"><span data-stu-id="2a667-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a667-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a667-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a667-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a667-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a667-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2a667-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a667-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a667-112">Attributes</span></span>  
  
|<span data-ttu-id="2a667-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2a667-113">Attribute</span></span>|<span data-ttu-id="2a667-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2a667-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a667-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="2a667-115">maxReadPoolSize</span></span>|<span data-ttu-id="2a667-116">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="2a667-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="2a667-117">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="2a667-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="2a667-118">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="2a667-118">The default is 64.</span></span>|  
|<span data-ttu-id="2a667-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="2a667-119">maxWritePoolSize</span></span>|<span data-ttu-id="2a667-120">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="2a667-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="2a667-121">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="2a667-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="2a667-122">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="2a667-122">The default is 16.</span></span>|  
|<span data-ttu-id="2a667-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="2a667-123">messageVersion</span></span>|<span data-ttu-id="2a667-124">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="2a667-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="2a667-125">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2a667-125">Valid values are</span></span><br /><br /> <span data-ttu-id="2a667-126">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="2a667-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="2a667-127">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="2a667-127">-   Soap12Addressing10</span></span><br /><span data-ttu-id="2a667-128">-Soap11</span><span class="sxs-lookup"><span data-stu-id="2a667-128">-   Soap11</span></span><br /><span data-ttu-id="2a667-129">-Soap12</span><span class="sxs-lookup"><span data-stu-id="2a667-129">-  Soap12</span></span><br /><br /><span data-ttu-id="2a667-130">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="2a667-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="2a667-131">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="2a667-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="2a667-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="2a667-132">writeEncoding</span></span>|<span data-ttu-id="2a667-133">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="2a667-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="2a667-134">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2a667-134">Valid values are</span></span><br /><br /> <span data-ttu-id="2a667-135">-Уникодефффетекстенкодинг: Кодировка байтов Юникода</span><span class="sxs-lookup"><span data-stu-id="2a667-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="2a667-136">- Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="2a667-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="2a667-137">- Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="2a667-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="2a667-138">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="2a667-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="2a667-139">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="2a667-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a667-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a667-140">Child Elements</span></span>  
  
|<span data-ttu-id="2a667-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a667-141">Element</span></span>|<span data-ttu-id="2a667-142">Описание</span><span class="sxs-lookup"><span data-stu-id="2a667-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a667-143">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2a667-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="2a667-144">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2a667-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2a667-145">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="2a667-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a667-146">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a667-146">Parent Elements</span></span>  
  
|<span data-ttu-id="2a667-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a667-147">Element</span></span>|<span data-ttu-id="2a667-148">Описание</span><span class="sxs-lookup"><span data-stu-id="2a667-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a667-149">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2a667-149">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2a667-150">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="2a667-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a667-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a667-151">Remarks</span></span>  
 <span data-ttu-id="2a667-152">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="2a667-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="2a667-153">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="2a667-153">Decoding is the reverse process.</span></span> <span data-ttu-id="2a667-154">Windows Communication Foundation (WCF) включает три типа кодировки для сообщений SOAP: Text, binary и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="2a667-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="2a667-155">Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="2a667-155">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="2a667-156">Кодировщик текста создает текстовые сообщения в сети.</span><span class="sxs-lookup"><span data-stu-id="2a667-156">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="2a667-157">Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-\*.</span><span class="sxs-lookup"><span data-stu-id="2a667-157">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="2a667-158">Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="2a667-158">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="2a667-159">Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="2a667-159">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a667-160">Пример</span><span class="sxs-lookup"><span data-stu-id="2a667-160">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="2a667-161">См. также</span><span class="sxs-lookup"><span data-stu-id="2a667-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="2a667-162">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="2a667-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="2a667-163">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="2a667-163">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="2a667-164">Привязки</span><span class="sxs-lookup"><span data-stu-id="2a667-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2a667-165">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="2a667-165">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2a667-166">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="2a667-166">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2a667-167">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2a667-167">\<customBinding></span></span>](custombinding.md)
