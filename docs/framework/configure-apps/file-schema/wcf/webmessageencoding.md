---
title: '&lt;webMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: fc1f83128dacb588d8179dea95c132da1ab2be91
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755270"
---
# <a name="ltwebmessageencodinggt"></a><span data-ttu-id="8b49e-102">&lt;webMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="8b49e-102">&lt;webMessageEncoding&gt;</span></span>
<span data-ttu-id="8b49e-103">Обеспечивает чтение и запись сообщений в виде обычного текста XML, сообщений в кодировке JSON (нотация объектов JavaScript), а также необработанного двоичного содержимого, используемого в привязке Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8b49e-103">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="8b49e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8b49e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8b49e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8b49e-105">\<bindings></span></span>  
<span data-ttu-id="8b49e-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8b49e-106">\<customBinding></span></span>  
<span data-ttu-id="8b49e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8b49e-107">\<binding></span></span>  
<span data-ttu-id="8b49e-108">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="8b49e-108">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b49e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b49e-109">Syntax</span></span>  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b49e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8b49e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8b49e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8b49e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b49e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8b49e-112">Attributes</span></span>  
  
|<span data-ttu-id="8b49e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8b49e-113">Attribute</span></span>|<span data-ttu-id="8b49e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8b49e-114">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="8b49e-115">Количество сообщений, которые можно читать одновременно, не выделяя памяти для новых обработчиков чтения.</span><span class="sxs-lookup"><span data-stu-id="8b49e-115">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="8b49e-116">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="8b49e-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8b49e-117">Значение по умолчанию - 64 обработчика чтения для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).</span><span class="sxs-lookup"><span data-stu-id="8b49e-117">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="8b49e-118">Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества входящих сообщений, позволяя использовать уже созданные обработчики чтения из пула, а не создавать новые.</span><span class="sxs-lookup"><span data-stu-id="8b49e-118">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="8b49e-119">Количество сообщений, которые можно отправить одновременно, не выделяя памяти для новых обработчиков записи.</span><span class="sxs-lookup"><span data-stu-id="8b49e-119">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="8b49e-120">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="8b49e-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8b49e-121">Значение по умолчанию - 16 обработчиков записи для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).</span><span class="sxs-lookup"><span data-stu-id="8b49e-121">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="8b49e-122">Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества исходящих сообщений, позволяя использовать уже созданные обработчики записи из пула, а не создавать новые.</span><span class="sxs-lookup"><span data-stu-id="8b49e-122">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="8b49e-123">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="8b49e-123">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="8b49e-124">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="8b49e-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="8b49e-125">-UnicodeFffeTextEncoding: Big Endian кодировку Юникод.</span><span class="sxs-lookup"><span data-stu-id="8b49e-125">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="8b49e-126">-Utf16TextEncoding: Кодировка Юникод.</span><span class="sxs-lookup"><span data-stu-id="8b49e-126">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="8b49e-127">-Utf8TextEncoding: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="8b49e-127">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="8b49e-128">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="8b49e-128">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="8b49e-129">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="8b49e-129">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b49e-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b49e-130">Child Elements</span></span>  
  
|<span data-ttu-id="8b49e-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b49e-131">Element</span></span>|<span data-ttu-id="8b49e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="8b49e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b49e-133">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="8b49e-133">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="8b49e-134">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="8b49e-134">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8b49e-135">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="8b49e-135">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b49e-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8b49e-136">Parent Elements</span></span>  
  
|<span data-ttu-id="8b49e-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b49e-137">Element</span></span>|<span data-ttu-id="8b49e-138">Описание</span><span class="sxs-lookup"><span data-stu-id="8b49e-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b49e-139">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8b49e-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8b49e-140">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="8b49e-140">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b49e-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b49e-141">Remarks</span></span>  
 <span data-ttu-id="8b49e-142">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="8b49e-142">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="8b49e-143">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="8b49e-143">Decoding is the reverse process.</span></span> <span data-ttu-id="8b49e-144">Эти процессы требуют определения кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="8b49e-144">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="8b49e-145">Элемент `webMessageEncoding` работает путем делегирования набору внутренних кодировщиков обработки кодировок XML (в формате обычного текста), JSON и двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="8b49e-145">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="8b49e-146">Делегирование выполняется с помощью составного кодировщика сообщений.</span><span class="sxs-lookup"><span data-stu-id="8b49e-146">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="8b49e-147">Этот элемент привязки и его составной кодировщик используются для управления кодировкой в тех сценариях, где не применяется обмен сообщениями по протоколу SOAP, используемый элементом `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="8b49e-147">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="8b49e-148">К таким сценариям относятся: Plain Old XML (POX), REST (Representational State Transfer), RSS (Really Simple Syndication), синдикация Atom и AJAX (Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="8b49e-148">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="8b49e-149">Составной кодировщик сообщений не поддерживает SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="8b49e-149">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="8b49e-150">В элементе привязки можно задать кодировку записи с помощью атрибута `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="8b49e-150">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="8b49e-151">Предоставленное значение <xref:System.Text.Encoding> задает поведение при записи для форматов JSON и XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="8b49e-151">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="8b49e-152">Для чтения поддерживается любая допустимая кодировка сообщений и кодировка текста.</span><span class="sxs-lookup"><span data-stu-id="8b49e-152">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="8b49e-153">Атрибуты `maxReadPoolSize` и `maxWritePoolSize` также могут использоваться для установки максимального количества выделяемых обработчиков чтения и записи соответственно.</span><span class="sxs-lookup"><span data-stu-id="8b49e-153">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="8b49e-154">По умолчанию выделяется 64 обработчика чтения и 16 обработчиков записи.</span><span class="sxs-lookup"><span data-stu-id="8b49e-154">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="8b49e-155">Ограничения по сложности по умолчанию также устанавливаются с использованием [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) элемент, чтобы защититься от отказ в обслуживании (DOS), направленных на сложность сообщения используется для перегрузки обработки конечной точки ресурсы.</span><span class="sxs-lookup"><span data-stu-id="8b49e-155">Default complexity constraints are also set using the [\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b49e-156">Пример</span><span class="sxs-lookup"><span data-stu-id="8b49e-156">Example</span></span>  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b49e-157">См. также</span><span class="sxs-lookup"><span data-stu-id="8b49e-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [<span data-ttu-id="8b49e-158">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="8b49e-158">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="8b49e-159">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="8b49e-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="8b49e-160">Привязки</span><span class="sxs-lookup"><span data-stu-id="8b49e-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8b49e-161">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8b49e-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8b49e-162">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8b49e-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8b49e-163">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8b49e-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
