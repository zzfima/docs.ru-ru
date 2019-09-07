---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 538591c85d91960eb4d4fa04caa945954ee5a997
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397706"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="57969-101">\<Мтоммессажеенкодинг ></span><span class="sxs-lookup"><span data-stu-id="57969-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="57969-102">Определяет метод шифрования и управления версиями сообщений для сообщений, использующих механизм оптимизации передачи сообщений SOAP (MTOM).</span><span class="sxs-lookup"><span data-stu-id="57969-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
<span data-ttu-id="57969-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="57969-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="57969-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="57969-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="57969-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="57969-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="57969-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="57969-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="57969-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="57969-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="57969-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Мтоммессажеенкодинг >**</span><span class="sxs-lookup"><span data-stu-id="57969-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57969-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57969-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57969-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="57969-110">Attributes and Elements</span></span>  
 <span data-ttu-id="57969-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="57969-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57969-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57969-112">Attributes</span></span>  
  
|<span data-ttu-id="57969-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="57969-113">Attribute</span></span>|<span data-ttu-id="57969-114">Описание</span><span class="sxs-lookup"><span data-stu-id="57969-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57969-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="57969-115">maxBufferSize</span></span>|<span data-ttu-id="57969-116">Целое число, задающее максимальный допустимый размер буфера.</span><span class="sxs-lookup"><span data-stu-id="57969-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="57969-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="57969-117">maxReadPoolSize</span></span>|<span data-ttu-id="57969-118">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="57969-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="57969-119">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="57969-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="57969-120">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="57969-120">The default is 64.</span></span>|  
|<span data-ttu-id="57969-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="57969-121">maxWritePoolSize</span></span>|<span data-ttu-id="57969-122">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="57969-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="57969-123">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="57969-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="57969-124">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="57969-124">The default is 16.</span></span>|  
|<span data-ttu-id="57969-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="57969-125">messageVersion</span></span>|<span data-ttu-id="57969-126">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="57969-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="57969-127">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="57969-127">Valid values are</span></span><br /><br /> <span data-ttu-id="57969-128">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="57969-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="57969-129">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="57969-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="57969-130">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="57969-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="57969-131">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="57969-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="57969-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="57969-132">writeEncoding</span></span>|<span data-ttu-id="57969-133">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="57969-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="57969-134">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="57969-134">Valid values are</span></span><br /><br /> <span data-ttu-id="57969-135">-Уникодефффетекстенкодинг: Кодировка байтов Юникода</span><span class="sxs-lookup"><span data-stu-id="57969-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="57969-136">- Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="57969-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="57969-137">- Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="57969-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="57969-138">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="57969-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="57969-139">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="57969-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57969-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57969-140">Child Elements</span></span>  
  
|<span data-ttu-id="57969-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="57969-141">Element</span></span>|<span data-ttu-id="57969-142">Описание</span><span class="sxs-lookup"><span data-stu-id="57969-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57969-143">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="57969-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="57969-144">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="57969-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="57969-145">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="57969-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57969-146">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57969-146">Parent Elements</span></span>  
  
|<span data-ttu-id="57969-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="57969-147">Element</span></span>|<span data-ttu-id="57969-148">Описание</span><span class="sxs-lookup"><span data-stu-id="57969-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57969-149">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="57969-149">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="57969-150">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="57969-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57969-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="57969-151">Remarks</span></span>  
 <span data-ttu-id="57969-152">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="57969-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="57969-153">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="57969-153">Decoding is the reverse process.</span></span> <span data-ttu-id="57969-154">Windows Communication Foundation (WCF) включает три типа кодировки для сообщений SOAP: Text, binary и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="57969-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="57969-155">Элемент `MtomMessageEncoding` указывает кодировку символов, управление версиями сообщений и другие параметры для сообщений, использующих кодировку MTOM.</span><span class="sxs-lookup"><span data-stu-id="57969-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="57969-156">MTOM - это эффективный способ передачи двоичных данных в сообщениях WCF.</span><span class="sxs-lookup"><span data-stu-id="57969-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="57969-157">Кодировщик MTOM пытается сохранить баланс между эффективностью и совместимостью.</span><span class="sxs-lookup"><span data-stu-id="57969-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="57969-158">При кодировке MTOM большая часть XML-кода передается в текстовой форме, однако выполняется оптимизация больших блоков двоичных данных путем передачи их в исходном виде, без преобразования их в базовый формат base64.</span><span class="sxs-lookup"><span data-stu-id="57969-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57969-159">Пример</span><span class="sxs-lookup"><span data-stu-id="57969-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="57969-160">См. также</span><span class="sxs-lookup"><span data-stu-id="57969-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="57969-161">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="57969-161">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="57969-162">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="57969-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="57969-163">Привязки</span><span class="sxs-lookup"><span data-stu-id="57969-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="57969-164">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="57969-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="57969-165">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="57969-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="57969-166">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="57969-166">\<customBinding></span></span>](custombinding.md)
