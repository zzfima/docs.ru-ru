---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 61b23957c56bad81598dd65b0dd68f7b44d329e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146800"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="62163-101">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="62163-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="62163-102">Определяет метод шифрования и управления версиями сообщений для сообщений, использующих механизм оптимизации передачи сообщений SOAP (MTOM).</span><span class="sxs-lookup"><span data-stu-id="62163-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="62163-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62163-103">\<system.serviceModel></span></span>  
<span data-ttu-id="62163-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="62163-104">\<bindings></span></span>  
<span data-ttu-id="62163-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="62163-105">\<customBinding></span></span>  
<span data-ttu-id="62163-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="62163-106">\<binding></span></span>  
<span data-ttu-id="62163-107">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="62163-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62163-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62163-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62163-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62163-109">Attributes and Elements</span></span>  
 <span data-ttu-id="62163-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62163-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62163-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62163-111">Attributes</span></span>  
  
|<span data-ttu-id="62163-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="62163-112">Attribute</span></span>|<span data-ttu-id="62163-113">Описание</span><span class="sxs-lookup"><span data-stu-id="62163-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62163-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="62163-114">maxBufferSize</span></span>|<span data-ttu-id="62163-115">Целое число, задающее максимальный допустимый размер буфера.</span><span class="sxs-lookup"><span data-stu-id="62163-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="62163-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="62163-116">maxReadPoolSize</span></span>|<span data-ttu-id="62163-117">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="62163-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="62163-118">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="62163-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="62163-119">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="62163-119">The default is 64.</span></span>|  
|<span data-ttu-id="62163-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="62163-120">maxWritePoolSize</span></span>|<span data-ttu-id="62163-121">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="62163-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="62163-122">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="62163-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="62163-123">Значение по умолчанию — 16.</span><span class="sxs-lookup"><span data-stu-id="62163-123">The default is 16.</span></span>|  
|<span data-ttu-id="62163-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="62163-124">messageVersion</span></span>|<span data-ttu-id="62163-125">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="62163-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="62163-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="62163-126">Valid values are</span></span><br /><br /> <span data-ttu-id="62163-127">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="62163-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="62163-128">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="62163-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="62163-129">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="62163-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="62163-130">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="62163-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="62163-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="62163-131">writeEncoding</span></span>|<span data-ttu-id="62163-132">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="62163-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="62163-133">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="62163-133">Valid values are</span></span><br /><br /> <span data-ttu-id="62163-134">-   UnicodeFffeTextEncoding: Юникод BigEndian</span><span class="sxs-lookup"><span data-stu-id="62163-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="62163-135">-   Utf16TextEncoding: Кодировка Юникод</span><span class="sxs-lookup"><span data-stu-id="62163-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="62163-136">-   Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="62163-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="62163-137">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="62163-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="62163-138">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="62163-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62163-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62163-139">Child Elements</span></span>  
  
|<span data-ttu-id="62163-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="62163-140">Element</span></span>|<span data-ttu-id="62163-141">Описание</span><span class="sxs-lookup"><span data-stu-id="62163-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62163-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="62163-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="62163-143">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="62163-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="62163-144">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="62163-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62163-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62163-145">Parent Elements</span></span>  
  
|<span data-ttu-id="62163-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="62163-146">Element</span></span>|<span data-ttu-id="62163-147">Описание</span><span class="sxs-lookup"><span data-stu-id="62163-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62163-148">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="62163-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="62163-149">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="62163-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62163-150">Примечания</span><span class="sxs-lookup"><span data-stu-id="62163-150">Remarks</span></span>  
 <span data-ttu-id="62163-151">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="62163-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="62163-152">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="62163-152">Decoding is the reverse process.</span></span> <span data-ttu-id="62163-153">Windows Communication Foundation (WCF) включает в себя три типа кодирования для сообщений SOAP: Текст, двоичное кодирование и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="62163-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="62163-154">Элемент `MtomMessageEncoding` указывает кодировку символов, управление версиями сообщений и другие параметры для сообщений, использующих кодировку MTOM.</span><span class="sxs-lookup"><span data-stu-id="62163-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="62163-155">MTOM - это эффективный способ передачи двоичных данных в сообщениях WCF.</span><span class="sxs-lookup"><span data-stu-id="62163-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="62163-156">Кодировщик MTOM пытается сохранить баланс между эффективностью и совместимостью.</span><span class="sxs-lookup"><span data-stu-id="62163-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="62163-157">При кодировке MTOM большая часть XML-кода передается в текстовой форме, однако выполняется оптимизация больших блоков двоичных данных путем передачи их в исходном виде, без преобразования их в базовый формат base64.</span><span class="sxs-lookup"><span data-stu-id="62163-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62163-158">Пример</span><span class="sxs-lookup"><span data-stu-id="62163-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="62163-159">См. также</span><span class="sxs-lookup"><span data-stu-id="62163-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="62163-160">Кодирование сообщений</span><span class="sxs-lookup"><span data-stu-id="62163-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="62163-161">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="62163-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="62163-162">Привязки</span><span class="sxs-lookup"><span data-stu-id="62163-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="62163-163">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="62163-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="62163-164">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="62163-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="62163-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="62163-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
