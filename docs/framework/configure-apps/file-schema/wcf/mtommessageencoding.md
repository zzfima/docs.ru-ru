---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 70a124fda5bc0e52e1271716f7e2166b7717b49a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933189"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="91f55-101">\<Мтоммессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="91f55-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="91f55-102">Определяет метод шифрования и управления версиями сообщений для сообщений, использующих механизм оптимизации передачи сообщений SOAP (MTOM).</span><span class="sxs-lookup"><span data-stu-id="91f55-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="91f55-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="91f55-103">\<system.serviceModel></span></span>  
<span data-ttu-id="91f55-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="91f55-104">\<bindings></span></span>  
<span data-ttu-id="91f55-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="91f55-105">\<customBinding></span></span>  
<span data-ttu-id="91f55-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="91f55-106">\<binding></span></span>  
<span data-ttu-id="91f55-107">\<Мтоммессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="91f55-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f55-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91f55-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91f55-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="91f55-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91f55-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="91f55-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91f55-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="91f55-111">Attributes</span></span>  
  
|<span data-ttu-id="91f55-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="91f55-112">Attribute</span></span>|<span data-ttu-id="91f55-113">Описание</span><span class="sxs-lookup"><span data-stu-id="91f55-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91f55-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="91f55-114">maxBufferSize</span></span>|<span data-ttu-id="91f55-115">Целое число, задающее максимальный допустимый размер буфера.</span><span class="sxs-lookup"><span data-stu-id="91f55-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="91f55-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="91f55-116">maxReadPoolSize</span></span>|<span data-ttu-id="91f55-117">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="91f55-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="91f55-118">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="91f55-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="91f55-119">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="91f55-119">The default is 64.</span></span>|  
|<span data-ttu-id="91f55-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="91f55-120">maxWritePoolSize</span></span>|<span data-ttu-id="91f55-121">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="91f55-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="91f55-122">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="91f55-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="91f55-123">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="91f55-123">The default is 16.</span></span>|  
|<span data-ttu-id="91f55-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="91f55-124">messageVersion</span></span>|<span data-ttu-id="91f55-125">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="91f55-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="91f55-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="91f55-126">Valid values are</span></span><br /><br /> <span data-ttu-id="91f55-127">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="91f55-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="91f55-128">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="91f55-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="91f55-129">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="91f55-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="91f55-130">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="91f55-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="91f55-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="91f55-131">writeEncoding</span></span>|<span data-ttu-id="91f55-132">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="91f55-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="91f55-133">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="91f55-133">Valid values are</span></span><br /><br /> <span data-ttu-id="91f55-134">-Уникодефффетекстенкодинг: Кодировка байтов Юникода</span><span class="sxs-lookup"><span data-stu-id="91f55-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="91f55-135">- Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="91f55-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="91f55-136">- Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="91f55-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="91f55-137">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="91f55-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="91f55-138">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="91f55-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91f55-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="91f55-139">Child Elements</span></span>  
  
|<span data-ttu-id="91f55-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="91f55-140">Element</span></span>|<span data-ttu-id="91f55-141">Описание</span><span class="sxs-lookup"><span data-stu-id="91f55-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91f55-142">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="91f55-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="91f55-143">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="91f55-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="91f55-144">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="91f55-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91f55-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="91f55-145">Parent Elements</span></span>  
  
|<span data-ttu-id="91f55-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="91f55-146">Element</span></span>|<span data-ttu-id="91f55-147">Описание</span><span class="sxs-lookup"><span data-stu-id="91f55-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91f55-148">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="91f55-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="91f55-149">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="91f55-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91f55-150">Примечания</span><span class="sxs-lookup"><span data-stu-id="91f55-150">Remarks</span></span>  
 <span data-ttu-id="91f55-151">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="91f55-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="91f55-152">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="91f55-152">Decoding is the reverse process.</span></span> <span data-ttu-id="91f55-153">Windows Communication Foundation (WCF) включает три типа кодировки для сообщений SOAP: Text, binary и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="91f55-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="91f55-154">Элемент `MtomMessageEncoding` указывает кодировку символов, управление версиями сообщений и другие параметры для сообщений, использующих кодировку MTOM.</span><span class="sxs-lookup"><span data-stu-id="91f55-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="91f55-155">MTOM - это эффективный способ передачи двоичных данных в сообщениях WCF.</span><span class="sxs-lookup"><span data-stu-id="91f55-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="91f55-156">Кодировщик MTOM пытается сохранить баланс между эффективностью и совместимостью.</span><span class="sxs-lookup"><span data-stu-id="91f55-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="91f55-157">При кодировке MTOM большая часть XML-кода передается в текстовой форме, однако выполняется оптимизация больших блоков двоичных данных путем передачи их в исходном виде, без преобразования их в базовый формат base64.</span><span class="sxs-lookup"><span data-stu-id="91f55-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91f55-158">Пример</span><span class="sxs-lookup"><span data-stu-id="91f55-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="91f55-159">См. также</span><span class="sxs-lookup"><span data-stu-id="91f55-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="91f55-160">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="91f55-160">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="91f55-161">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="91f55-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="91f55-162">Привязки</span><span class="sxs-lookup"><span data-stu-id="91f55-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="91f55-163">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="91f55-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="91f55-164">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="91f55-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="91f55-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="91f55-165">\<customBinding></span></span>](custombinding.md)
