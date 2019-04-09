---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e9942ce3ccbec949160ee70dd103d3c1799bd44d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186307"
---
# <a name="textmessageencoding"></a><span data-ttu-id="b6c3b-101">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-101">\<textMessageEncoding></span></span>
<span data-ttu-id="b6c3b-102">Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="b6c3b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6c3b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b6c3b-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-104">\<bindings></span></span>  
<span data-ttu-id="b6c3b-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-105">\<customBinding></span></span>  
<span data-ttu-id="b6c3b-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-106">\<binding></span></span>  
<span data-ttu-id="b6c3b-107">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c3b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6c3b-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6c3b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6c3b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b6c3b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6c3b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6c3b-111">Attributes</span></span>  
  
|<span data-ttu-id="b6c3b-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6c3b-112">Attribute</span></span>|<span data-ttu-id="b6c3b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b6c3b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6c3b-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="b6c3b-114">maxReadPoolSize</span></span>|<span data-ttu-id="b6c3b-115">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="b6c3b-116">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="b6c3b-117">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-117">The default is 64.</span></span>|  
|<span data-ttu-id="b6c3b-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="b6c3b-118">maxWritePoolSize</span></span>|<span data-ttu-id="b6c3b-119">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="b6c3b-120">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="b6c3b-121">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-121">The default is 16.</span></span>|  
|<span data-ttu-id="b6c3b-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b6c3b-122">messageVersion</span></span>|<span data-ttu-id="b6c3b-123">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b6c3b-124">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b6c3b-124">Valid values are</span></span><br /><br /> <span data-ttu-id="b6c3b-125">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="b6c3b-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="b6c3b-126">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="b6c3b-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="b6c3b-127">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="b6c3b-128">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="b6c3b-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="b6c3b-129">writeEncoding</span></span>|<span data-ttu-id="b6c3b-130">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b6c3b-131">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b6c3b-131">Valid values are</span></span><br /><br /> <span data-ttu-id="b6c3b-132">-   UnicodeFffeTextEncoding: Юникод BigEndian</span><span class="sxs-lookup"><span data-stu-id="b6c3b-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="b6c3b-133">-   Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="b6c3b-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="b6c3b-134">-   Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="b6c3b-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="b6c3b-135">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="b6c3b-136">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6c3b-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6c3b-137">Child Elements</span></span>  
  
|<span data-ttu-id="b6c3b-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6c3b-138">Element</span></span>|<span data-ttu-id="b6c3b-139">Описание</span><span class="sxs-lookup"><span data-stu-id="b6c3b-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6c3b-140">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="b6c3b-140">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="b6c3b-141">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b6c3b-142">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6c3b-143">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6c3b-143">Parent Elements</span></span>  
  
|<span data-ttu-id="b6c3b-144">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6c3b-144">Element</span></span>|<span data-ttu-id="b6c3b-145">Описание</span><span class="sxs-lookup"><span data-stu-id="b6c3b-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6c3b-146">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b6c3b-147">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6c3b-148">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6c3b-148">Remarks</span></span>  
 <span data-ttu-id="b6c3b-149">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="b6c3b-150">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-150">Decoding is the reverse process.</span></span> <span data-ttu-id="b6c3b-151">Windows Communication Foundation (WCF) включает в себя три типа кодирования для сообщений SOAP: Текст, двоичное кодирование и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="b6c3b-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="b6c3b-152">Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="b6c3b-153">Кодировщик текста создает текстовые сообщения в сети.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="b6c3b-154">Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-\*.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="b6c3b-155">Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="b6c3b-156">Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="b6c3b-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6c3b-157">Пример</span><span class="sxs-lookup"><span data-stu-id="b6c3b-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b6c3b-158">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c3b-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="b6c3b-159">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="b6c3b-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b6c3b-160">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="b6c3b-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="b6c3b-161">Привязки</span><span class="sxs-lookup"><span data-stu-id="b6c3b-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b6c3b-162">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b6c3b-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b6c3b-163">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b6c3b-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b6c3b-164">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b6c3b-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
