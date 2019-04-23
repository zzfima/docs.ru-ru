---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: 7221f19dd131dbd60ef1a61625633d54dfdbe85a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191748"
---
# <a name="webmessageencoding"></a><span data-ttu-id="0f262-101">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="0f262-101">\<webMessageEncoding></span></span>
<span data-ttu-id="0f262-102">Обеспечивает чтение и запись сообщений в виде обычного текста XML, сообщений в кодировке JSON (нотация объектов JavaScript), а также необработанного двоичного содержимого, используемого в привязке Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0f262-102">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="0f262-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0f262-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0f262-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="0f262-104">\<bindings></span></span>  
<span data-ttu-id="0f262-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0f262-105">\<customBinding></span></span>  
<span data-ttu-id="0f262-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0f262-106">\<binding></span></span>  
<span data-ttu-id="0f262-107">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="0f262-107">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f262-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f262-108">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f262-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f262-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0f262-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f262-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f262-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f262-111">Attributes</span></span>  
  
|<span data-ttu-id="0f262-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0f262-112">Attribute</span></span>|<span data-ttu-id="0f262-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0f262-113">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="0f262-114">Количество сообщений, которые можно читать одновременно, не выделяя памяти для новых обработчиков чтения.</span><span class="sxs-lookup"><span data-stu-id="0f262-114">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="0f262-115">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="0f262-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0f262-116">Значение по умолчанию - 64 обработчика чтения для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).</span><span class="sxs-lookup"><span data-stu-id="0f262-116">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="0f262-117">Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества входящих сообщений, позволяя использовать уже созданные обработчики чтения из пула, а не создавать новые.</span><span class="sxs-lookup"><span data-stu-id="0f262-117">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="0f262-118">Количество сообщений, которые можно отправить одновременно, не выделяя памяти для новых обработчиков записи.</span><span class="sxs-lookup"><span data-stu-id="0f262-118">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="0f262-119">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="0f262-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0f262-120">Значение по умолчанию - 16 обработчиков записи для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).</span><span class="sxs-lookup"><span data-stu-id="0f262-120">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="0f262-121">Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества исходящих сообщений, позволяя использовать уже созданные обработчики записи из пула, а не создавать новые.</span><span class="sxs-lookup"><span data-stu-id="0f262-121">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="0f262-122">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="0f262-122">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="0f262-123">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0f262-123">Valid values are:</span></span><br /><br /> <span data-ttu-id="0f262-124">-   UnicodeFffeTextEncoding: Обратный порядок байтов кодировка Юникод.</span><span class="sxs-lookup"><span data-stu-id="0f262-124">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="0f262-125">-   Utf16TextEncoding: Кодировка Юникод.</span><span class="sxs-lookup"><span data-stu-id="0f262-125">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="0f262-126">-   Utf8TextEncoding: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="0f262-126">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="0f262-127">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="0f262-127">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="0f262-128">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="0f262-128">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f262-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f262-129">Child Elements</span></span>  
  
|<span data-ttu-id="0f262-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f262-130">Element</span></span>|<span data-ttu-id="0f262-131">Описание</span><span class="sxs-lookup"><span data-stu-id="0f262-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f262-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0f262-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="0f262-133">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="0f262-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0f262-134">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0f262-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f262-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f262-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0f262-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f262-136">Element</span></span>|<span data-ttu-id="0f262-137">Описание</span><span class="sxs-lookup"><span data-stu-id="0f262-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f262-138">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="0f262-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0f262-139">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="0f262-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f262-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f262-140">Remarks</span></span>  
 <span data-ttu-id="0f262-141">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="0f262-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="0f262-142">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="0f262-142">Decoding is the reverse process.</span></span> <span data-ttu-id="0f262-143">Эти процессы требуют определения кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="0f262-143">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="0f262-144">Элемент `webMessageEncoding` работает путем делегирования набору внутренних кодировщиков обработки кодировок XML (в формате обычного текста), JSON и двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="0f262-144">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="0f262-145">Делегирование выполняется с помощью составного кодировщика сообщений.</span><span class="sxs-lookup"><span data-stu-id="0f262-145">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="0f262-146">Этот элемент привязки и его составной кодировщик используются для управления кодировкой в тех сценариях, где не применяется обмен сообщениями по протоколу SOAP, используемый элементом `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="0f262-146">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="0f262-147">К таким сценариям относятся: Plain Old XML (POX), REST (Representational State Transfer), RSS (Really Simple Syndication), синдикация Atom и AJAX (Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="0f262-147">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="0f262-148">Составной кодировщик сообщений не поддерживает SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="0f262-148">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="0f262-149">В элементе привязки можно задать кодировку записи с помощью атрибута `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="0f262-149">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="0f262-150">Предоставленное значение <xref:System.Text.Encoding> задает поведение при записи для форматов JSON и XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="0f262-150">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="0f262-151">Для чтения поддерживается любая допустимая кодировка сообщений и кодировка текста.</span><span class="sxs-lookup"><span data-stu-id="0f262-151">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="0f262-152">Атрибуты `maxReadPoolSize` и `maxWritePoolSize` также могут использоваться для установки максимального количества выделяемых обработчиков чтения и записи соответственно.</span><span class="sxs-lookup"><span data-stu-id="0f262-152">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="0f262-153">По умолчанию выделяется 64 обработчика чтения и 16 обработчиков записи.</span><span class="sxs-lookup"><span data-stu-id="0f262-153">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="0f262-154">По умолчанию ограничения по сложности также задаются [ \<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) элемент, чтобы обеспечить защиту от класса отказ в обслуживании (DOS), направленных на сложность сообщения используется для перегрузки обработки конечной точки ресурсы.</span><span class="sxs-lookup"><span data-stu-id="0f262-154">Default complexity constraints are also set using the [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f262-155">Пример</span><span class="sxs-lookup"><span data-stu-id="0f262-155">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0f262-156">См. также</span><span class="sxs-lookup"><span data-stu-id="0f262-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="0f262-157">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="0f262-157">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="0f262-158">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="0f262-158">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="0f262-159">Привязки</span><span class="sxs-lookup"><span data-stu-id="0f262-159">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0f262-160">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="0f262-160">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0f262-161">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="0f262-161">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0f262-162">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0f262-162">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
