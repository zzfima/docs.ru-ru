---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e2fec2c2e5979b08ed0d832f636b3d0847b9a5dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915662"
---
# <a name="textmessageencoding"></a><span data-ttu-id="e7f56-101">\<Текстмессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="e7f56-101">\<textMessageEncoding></span></span>
<span data-ttu-id="e7f56-102">Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="e7f56-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="e7f56-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="e7f56-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e7f56-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e7f56-104">\<bindings></span></span>  
<span data-ttu-id="e7f56-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7f56-105">\<customBinding></span></span>  
<span data-ttu-id="e7f56-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e7f56-106">\<binding></span></span>  
<span data-ttu-id="e7f56-107">\<Текстмессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="e7f56-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f56-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7f56-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f56-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7f56-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f56-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7f56-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f56-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7f56-111">Attributes</span></span>  
  
|<span data-ttu-id="e7f56-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7f56-112">Attribute</span></span>|<span data-ttu-id="e7f56-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f56-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7f56-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e7f56-114">maxReadPoolSize</span></span>|<span data-ttu-id="e7f56-115">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="e7f56-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e7f56-116">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="e7f56-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e7f56-117">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="e7f56-117">The default is 64.</span></span>|  
|<span data-ttu-id="e7f56-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e7f56-118">maxWritePoolSize</span></span>|<span data-ttu-id="e7f56-119">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="e7f56-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e7f56-120">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="e7f56-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e7f56-121">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="e7f56-121">The default is 16.</span></span>|  
|<span data-ttu-id="e7f56-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e7f56-122">messageVersion</span></span>|<span data-ttu-id="e7f56-123">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="e7f56-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="e7f56-124">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e7f56-124">Valid values are</span></span><br /><br /> <span data-ttu-id="e7f56-125">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="e7f56-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="e7f56-126">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="e7f56-126">-   Soap12Addressing10</span></span><br /><span data-ttu-id="e7f56-127">-Soap11</span><span class="sxs-lookup"><span data-stu-id="e7f56-127">-   Soap11</span></span><br /><span data-ttu-id="e7f56-128">-Soap12</span><span class="sxs-lookup"><span data-stu-id="e7f56-128">-  Soap12</span></span><br /><br /><span data-ttu-id="e7f56-129">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="e7f56-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="e7f56-130">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="e7f56-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="e7f56-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="e7f56-131">writeEncoding</span></span>|<span data-ttu-id="e7f56-132">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="e7f56-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="e7f56-133">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e7f56-133">Valid values are</span></span><br /><br /> <span data-ttu-id="e7f56-134">-Уникодефффетекстенкодинг: Кодировка байтов Юникода</span><span class="sxs-lookup"><span data-stu-id="e7f56-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="e7f56-135">- Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="e7f56-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="e7f56-136">- Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="e7f56-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="e7f56-137">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="e7f56-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="e7f56-138">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="e7f56-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f56-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7f56-139">Child Elements</span></span>  
  
|<span data-ttu-id="e7f56-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7f56-140">Element</span></span>|<span data-ttu-id="e7f56-141">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f56-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7f56-142">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e7f56-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e7f56-143">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="e7f56-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e7f56-144">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e7f56-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f56-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7f56-145">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f56-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7f56-146">Element</span></span>|<span data-ttu-id="e7f56-147">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f56-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7f56-148">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e7f56-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="e7f56-149">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e7f56-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f56-150">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7f56-150">Remarks</span></span>  
 <span data-ttu-id="e7f56-151">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="e7f56-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e7f56-152">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="e7f56-152">Decoding is the reverse process.</span></span> <span data-ttu-id="e7f56-153">Windows Communication Foundation (WCF) включает три типа кодировки для сообщений SOAP: Text, binary и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="e7f56-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e7f56-154">Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="e7f56-154">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="e7f56-155">Кодировщик текста создает текстовые сообщения в сети.</span><span class="sxs-lookup"><span data-stu-id="e7f56-155">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="e7f56-156">Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-\*.</span><span class="sxs-lookup"><span data-stu-id="e7f56-156">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="e7f56-157">Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="e7f56-157">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="e7f56-158">Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="e7f56-158">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7f56-159">Пример</span><span class="sxs-lookup"><span data-stu-id="e7f56-159">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e7f56-160">См. также</span><span class="sxs-lookup"><span data-stu-id="e7f56-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="e7f56-161">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="e7f56-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e7f56-162">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="e7f56-162">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="e7f56-163">Привязки</span><span class="sxs-lookup"><span data-stu-id="e7f56-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e7f56-164">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e7f56-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7f56-165">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e7f56-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e7f56-166">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7f56-166">\<customBinding></span></span>](custombinding.md)
