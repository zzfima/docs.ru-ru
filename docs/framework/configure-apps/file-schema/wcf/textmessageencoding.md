---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 640cf8fce766f7107e297143e061f4f60d9f263d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753486"
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="4cca5-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="4cca5-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="4cca5-103">Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="4cca5-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="4cca5-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4cca5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4cca5-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4cca5-105">\<bindings></span></span>  
<span data-ttu-id="4cca5-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4cca5-106">\<customBinding></span></span>  
<span data-ttu-id="4cca5-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4cca5-107">\<binding></span></span>  
<span data-ttu-id="4cca5-108">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="4cca5-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cca5-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cca5-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cca5-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4cca5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4cca5-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4cca5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cca5-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4cca5-112">Attributes</span></span>  
  
|<span data-ttu-id="4cca5-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4cca5-113">Attribute</span></span>|<span data-ttu-id="4cca5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4cca5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4cca5-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4cca5-115">maxReadPoolSize</span></span>|<span data-ttu-id="4cca5-116">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="4cca5-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4cca5-117">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="4cca5-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4cca5-118">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="4cca5-118">The default is 64.</span></span>|  
|<span data-ttu-id="4cca5-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4cca5-119">maxWritePoolSize</span></span>|<span data-ttu-id="4cca5-120">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="4cca5-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4cca5-121">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="4cca5-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4cca5-122">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="4cca5-122">The default is 16.</span></span>|  
|<span data-ttu-id="4cca5-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4cca5-123">messageVersion</span></span>|<span data-ttu-id="4cca5-124">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="4cca5-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4cca5-125">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4cca5-125">Valid values are</span></span><br /><br /> <span data-ttu-id="4cca5-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="4cca5-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="4cca5-127">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="4cca5-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="4cca5-128">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="4cca5-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="4cca5-129">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="4cca5-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="4cca5-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="4cca5-130">writeEncoding</span></span>|<span data-ttu-id="4cca5-131">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="4cca5-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4cca5-132">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4cca5-132">Valid values are</span></span><br /><br /> <span data-ttu-id="4cca5-133">-UnicodeFffeTextEncoding: Юникод BigEndian</span><span class="sxs-lookup"><span data-stu-id="4cca5-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="4cca5-134">-Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="4cca5-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="4cca5-135">-Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="4cca5-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4cca5-136">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="4cca5-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4cca5-137">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4cca5-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cca5-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4cca5-138">Child Elements</span></span>  
  
|<span data-ttu-id="4cca5-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="4cca5-139">Element</span></span>|<span data-ttu-id="4cca5-140">Описание</span><span class="sxs-lookup"><span data-stu-id="4cca5-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cca5-141">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="4cca5-141">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="4cca5-142">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="4cca5-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4cca5-143">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4cca5-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4cca5-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4cca5-144">Parent Elements</span></span>  
  
|<span data-ttu-id="4cca5-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="4cca5-145">Element</span></span>|<span data-ttu-id="4cca5-146">Описание</span><span class="sxs-lookup"><span data-stu-id="4cca5-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cca5-147">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4cca5-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4cca5-148">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="4cca5-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cca5-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="4cca5-149">Remarks</span></span>  
 <span data-ttu-id="4cca5-150">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="4cca5-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4cca5-151">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="4cca5-151">Decoding is the reverse process.</span></span> <span data-ttu-id="4cca5-152">В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.</span><span class="sxs-lookup"><span data-stu-id="4cca5-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4cca5-153">Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="4cca5-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="4cca5-154">Кодировщик текста создает текстовые сообщения в сети.</span><span class="sxs-lookup"><span data-stu-id="4cca5-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="4cca5-155">Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-\*.</span><span class="sxs-lookup"><span data-stu-id="4cca5-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="4cca5-156">Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="4cca5-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="4cca5-157">Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="4cca5-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cca5-158">Пример</span><span class="sxs-lookup"><span data-stu-id="4cca5-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cca5-159">См. также</span><span class="sxs-lookup"><span data-stu-id="4cca5-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="4cca5-160">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="4cca5-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="4cca5-161">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="4cca5-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="4cca5-162">Привязки</span><span class="sxs-lookup"><span data-stu-id="4cca5-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4cca5-163">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4cca5-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4cca5-164">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4cca5-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4cca5-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4cca5-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
