---
title: Протоколы обмена сообщениями
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 7d94b917f3d8d2fd7faed28b9320edc240724e0b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46478973"
---
# <a name="messaging-protocols"></a><span data-ttu-id="e410e-102">Протоколы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="e410e-102">Messaging Protocols</span></span>

<span data-ttu-id="e410e-103">Стек канала Windows Communication Foundation (WCF) использует шифрование и транспортные каналы для преобразования представления внутренних сообщений в его формат подключения и отправить его с помощью определенного транспорта.</span><span class="sxs-lookup"><span data-stu-id="e410e-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="e410e-104">Для взаимодействия веб-служб чаще всего используется транспорт HTTP, а в качестве кодировок в веб-службах чаще всего используются основанные на XML протоколы SOAP 1.1, SOAP 1.2 и механизм оптимизации передачи сообщений (MTOM).</span><span class="sxs-lookup"><span data-stu-id="e410e-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>

<span data-ttu-id="e410e-105">В этом разделе рассматриваются подробные сведения о реализации WCF для следующих протоколов, используемых <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="e410e-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>

<span data-ttu-id="e410e-106">Спецификации:</span><span class="sxs-lookup"><span data-stu-id="e410e-106">Specification/document:</span></span>

- [<span data-ttu-id="e410e-107">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="e410e-107">HTTP 1.1</span></span>](https://www.ietf.org/rfc/rfc2616.txt)
- <span data-ttu-id="e410e-108">[Привязка SOAP 1.1 HTTP](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), раздел 7</span><span class="sxs-lookup"><span data-stu-id="e410e-108">[SOAP 1.1 HTTP Binding](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Section 7</span></span>
- <span data-ttu-id="e410e-109">[Привязка SOAP 1,2 HTTP](https://www.w3.org/TR/soap12-part2) раздел 7</span><span class="sxs-lookup"><span data-stu-id="e410e-109">[SOAP 1.2 HTTP Binding](https://www.w3.org/TR/soap12-part2) Section 7</span></span>

<span data-ttu-id="e410e-110">В этом разделе рассматриваются подробные сведения о реализации WCF для перечисленных ниже протоколов <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> использовать.</span><span class="sxs-lookup"><span data-stu-id="e410e-110">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>

<span data-ttu-id="e410e-111">Спецификации:</span><span class="sxs-lookup"><span data-stu-id="e410e-111">Specification/Document:</span></span>

- [<span data-ttu-id="e410e-112">XML</span><span class="sxs-lookup"><span data-stu-id="e410e-112">XML</span></span>](https://www.w3.org/TR/REC-xml)
- [<span data-ttu-id="e410e-113">SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="e410e-113">SOAP 1.1</span></span>](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [<span data-ttu-id="e410e-114">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="e410e-114">SOAP 1.2 Core</span></span>](https://www.w3.org/TR/soap12-part1/)
- [<span data-ttu-id="e410e-115">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="e410e-115">WS-Addressing 2004/08</span></span>](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [<span data-ttu-id="e410e-116">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="e410e-116">W3C Web Services Addressing 1.0 - Core</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [<span data-ttu-id="e410e-117">W3C Web Services Addressing 1.0 - привязка SOAP</span><span class="sxs-lookup"><span data-stu-id="e410e-117">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [<span data-ttu-id="e410e-118">W3C Web Services Addressing 1.0 - привязка WSDL</span><span class="sxs-lookup"><span data-stu-id="e410e-118">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [<span data-ttu-id="e410e-119">W3C Web Services Addressing 1.0 - метаданные</span><span class="sxs-lookup"><span data-stu-id="e410e-119">W3C Web Services Addressing 1.0 - Metadata</span></span>](https://www.w3.org/TR/ws-addr-metadata/)
- [<span data-ttu-id="e410e-120">Привязка WSDL SOAP1.1</span><span class="sxs-lookup"><span data-stu-id="e410e-120">WSDL SOAP1.1 Binding</span></span>](https://www.w3.org/TR/wsdl/)
- [<span data-ttu-id="e410e-121">Привязка WSDL SOAP1.2</span><span class="sxs-lookup"><span data-stu-id="e410e-121">WSDL SOAP1.2 Binding</span></span>](https://www.w3.org/Submission/wsdl11soap12/)

<span data-ttu-id="e410e-122">В этом разделе рассматриваются подробные сведения о реализации WCF для перечисленных ниже протоколов <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> использует.</span><span class="sxs-lookup"><span data-stu-id="e410e-122">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>

<span data-ttu-id="e410e-123">Спецификации:</span><span class="sxs-lookup"><span data-stu-id="e410e-123">Specification/document:</span></span>

- [<span data-ttu-id="e410e-124">XOP</span><span class="sxs-lookup"><span data-stu-id="e410e-124">XOP</span></span>](https://www.w3.org/TR/xop10/)
- [<span data-ttu-id="e410e-125">MTOM + SOAP 1.2 привязки</span><span class="sxs-lookup"><span data-stu-id="e410e-125">MTOM + SOAP 1.2 Binding</span></span>](https://www.w3.org/TR/soap12-mtom/)
- [<span data-ttu-id="e410e-126">Привязка MTOM SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="e410e-126">MTOM SOAP 1.1 Binding</span></span>](https://www.w3.org/Submission/soap11mtom10/)
- [<span data-ttu-id="e410e-127">Утверждение WS-Policy для MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-127">MTOM WS-Policy Assertion</span></span>](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

<span data-ttu-id="e410e-128">В этом разделе используются следующие пространства имен XML и связанные с ними префиксы.</span><span class="sxs-lookup"><span data-stu-id="e410e-128">The following XML namespaces and associated prefixes are used throughout this topic:</span></span>

<span data-ttu-id="e410e-129">| Префикс | Равномерное распределение пространства имен ресурса (URI) | [---|---| | s11 | `http://schemas.xmlsoap.org/soap/envelope`| | s12 | `http://www.w3.org/2003/05/soap-envelope`| | wsa | `http://www.w3.org/2004/08/addressing`| | wsam | `http://www.w3.org/2007/05/addressing/metadata`| | wsap | `http://schemas.xmlsoap.org/ws/2004/09/policy/addressing`| | wsa10 | `http://www.w3.org/2005/08/addressing`| | wsaw10 | `http://www.w3.org/2006/05/addressing/wsdl`| | xop | `http://www.w3.org/2004/08/xop/include`| | xmime |`http://www.w3.org/2004/06/xmlmime`</span><span class="sxs-lookup"><span data-stu-id="e410e-129">|Prefix|Namespace Uniform Resource Identifier (URI)| [------------|---------------------------------------------------| |s11|`http://schemas.xmlsoap.org/soap/envelope`| |s12|`http://www.w3.org/2003/05/soap-envelope`| |wsa|`http://www.w3.org/2004/08/addressing`| |wsam|`http://www.w3.org/2007/05/addressing/metadata`| |wsap|`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing`| |wsa10|`http://www.w3.org/2005/08/addressing`| |wsaw10|`http://www.w3.org/2006/05/addressing/wsdl`| |xop|`http://www.w3.org/2004/08/xop/include`| |xmime|`http://www.w3.org/2004/06/xmlmime`</span></span><br /><br /> <span data-ttu-id="e410e-130">`http://www.w3.org/2005/05/xmlmime`| | dp |`http://schemas.microsoft.com/net/2006/06/duplex`|</span><span class="sxs-lookup"><span data-stu-id="e410e-130">`http://www.w3.org/2005/05/xmlmime`| |dp|`http://schemas.microsoft.com/net/2006/06/duplex`|</span></span>

## <a name="soap-11-and-soap-12"></a><span data-ttu-id="e410e-131">SOAP 1.1 и SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="e410e-131">SOAP 1.1 and SOAP 1.2</span></span>

### <a name="envelope-and-processing-model"></a><span data-ttu-id="e410e-132">Конверт и модель обработки</span><span class="sxs-lookup"><span data-stu-id="e410e-132">Envelope and Processing Model</span></span>
<span data-ttu-id="e410e-133">В WCF реализована обработка конверта SOAP 1.1, следуя Basic Profile 1.1 (BP11) и Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="e410e-133">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="e410e-134">Обработка конверта SOAP 1.2 реализована в соответствии со спецификацией SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="e410e-134">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>

<span data-ttu-id="e410e-135">В этом разделе объясняется, некоторые варианты реализации, выбранные платформой WCF отношении спецификаций BP11 и SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="e410e-135">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>

#### <a name="mandatory-header-processing"></a><span data-ttu-id="e410e-136">Обработка обязательных заголовков</span><span class="sxs-lookup"><span data-stu-id="e410e-136">Mandatory Header Processing</span></span>
<span data-ttu-id="e410e-137">WCF следует правилам для обработки заголовков, помеченных `mustUnderstand` описано в спецификации SOAP 1.1 и SOAP 1.2, со следующими вариациями.</span><span class="sxs-lookup"><span data-stu-id="e410e-137">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>

<span data-ttu-id="e410e-138">Сообщение, которое поступает в стек канала WCF, обрабатывается отдельными каналами, настроенными с связанных элементов привязки, например, текстовое кодирование сообщений, безопасности, надежного обмена сообщениями и транзакций.</span><span class="sxs-lookup"><span data-stu-id="e410e-138">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="e410e-139">Каждый канал распознает заголовки из связанного пространства имен и помечает их как распознанные.</span><span class="sxs-lookup"><span data-stu-id="e410e-139">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="e410e-140">После поступления сообщения в диспетчер модуль форматирования операций считывает заголовки, ожидаемые соответствующим контрактом сообщения/операции, и помечает их как распознанные.</span><span class="sxs-lookup"><span data-stu-id="e410e-140">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="e410e-141">Затем диспетчер проверяет, не остались ли нераспознанные заголовки, помеченные как `mustUnderstand`, и создает исключение.</span><span class="sxs-lookup"><span data-stu-id="e410e-141">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="e410e-142">Сообщения, содержащие заголовки `mustUnderstand` и предназначенные получателю, не обрабатываются кодом приложения получателя.</span><span class="sxs-lookup"><span data-stu-id="e410e-142">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>

<span data-ttu-id="e410e-143">Такая многоуровневая обработка обеспечивает разделение уровней инфраструктуры и уровней приложения узла SOAP:</span><span class="sxs-lookup"><span data-stu-id="e410e-143">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>

- <span data-ttu-id="e410e-144">B1111: Нераспознанные заголовки обнаруживаются после обработки сообщения стеком каналов инфраструктуры WCF, но до его обработки приложением</span><span class="sxs-lookup"><span data-stu-id="e410e-144">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>

     <span data-ttu-id="e410e-145">Значения заголовка `mustUnderstand` в SOAP 1.1 и SOAP 1.2 различаются.</span><span class="sxs-lookup"><span data-stu-id="e410e-145">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="e410e-146">Профиль Basic Profile 1.1 требует, чтобы для сообщений SOAP 1.1 значение параметра `mustUnderstand` было равно 0 или 1.</span><span class="sxs-lookup"><span data-stu-id="e410e-146">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="e410e-147">В спецификации SOAP 1.2 допускаются значения 0, 1, `false` и `true`, но рекомендуется использовать каноническое представление значений `xs:boolean` (`false`, `true`).</span><span class="sxs-lookup"><span data-stu-id="e410e-147">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>

- <span data-ttu-id="e410e-148">B1112: WCF выдает `mustUnderstand` значения 0 и 1 для версий SOAP 1.1 и SOAP 1.2 конверта SOAP.</span><span class="sxs-lookup"><span data-stu-id="e410e-148">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="e410e-149">WCF принимает полное пространство значений `xs:boolean` для `mustUnderstand` заголовка (0, 1, `false`, `true`)</span><span class="sxs-lookup"><span data-stu-id="e410e-149">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>

#### <a name="soap-faults"></a><span data-ttu-id="e410e-150">Ошибки SOAP</span><span class="sxs-lookup"><span data-stu-id="e410e-150">SOAP Faults</span></span>
<span data-ttu-id="e410e-151">Ниже приведен список реализаций ошибок SOAP относящиеся конкретно к WCF.</span><span class="sxs-lookup"><span data-stu-id="e410e-151">The following is a list of WCF-specific SOAP fault implementations.</span></span>

- <span data-ttu-id="e410e-152">B2121: WCF возвращает следующие коды ошибок SOAP 1.1: `s11:mustUnderstand`, `s11:Client`, и `s11:Server`.</span><span class="sxs-lookup"><span data-stu-id="e410e-152">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>

- <span data-ttu-id="e410e-153">B2122: WCF возвращает следующие коды ошибок SOAP 1.2: `s12:MustUnderstand`, `s12:Sender`, и `s12:Receiver`.</span><span class="sxs-lookup"><span data-stu-id="e410e-153">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>

### <a name="http-binding"></a><span data-ttu-id="e410e-154">Привязка HTTP</span><span class="sxs-lookup"><span data-stu-id="e410e-154">HTTP Binding</span></span>

#### <a name="soap-11-http-binding"></a><span data-ttu-id="e410e-155">Привязка SOAP 1.1 HTTP</span><span class="sxs-lookup"><span data-stu-id="e410e-155">SOAP 1.1 HTTP Binding</span></span>
<span data-ttu-id="e410e-156">WCF реализует привязку SOAP1.1 HTTP в спецификации Basic Profile 1.1, раздел 3.4 со следующими уточнениями:</span><span class="sxs-lookup"><span data-stu-id="e410e-156">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>

- <span data-ttu-id="e410e-157">B2211: Служба WCF не реализует перенаправление запросов HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="e410e-157">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>

- <span data-ttu-id="e410e-158">B2212: Клиенты WCF поддерживают файлы cookie HTTP, в соответствии с 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="e410e-158">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>

#### <a name="soap-12-http-binding"></a><span data-ttu-id="e410e-159">Привязка SOAP 1,2 HTTP</span><span class="sxs-lookup"><span data-stu-id="e410e-159">SOAP 1.2 HTTP Binding</span></span>
<span data-ttu-id="e410e-160">WCF реализует привязку SOAP 1.2 HTTP, как описано в SOAP 1.2-part 2 (soap12part2) со следующими уточнениями.</span><span class="sxs-lookup"><span data-stu-id="e410e-160">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>

<span data-ttu-id="e410e-161">В SOAP 1.2 введен необязательный параметр действия для типа носителя `application/soap+xml`.</span><span class="sxs-lookup"><span data-stu-id="e410e-161">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="e410e-162">Этот параметр полезен для оптимизации распределения сообщений без необходимости анализа тела сообщения SOAP, если не используется протокол WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="e410e-162">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>

- <span data-ttu-id="e410e-163">R2221: параметр действия `application/soap+xml`, если он присутствует в запросе SOAP 1.2, должен соответствовать атрибуту `soapAction` элемента `wsoap12:operation` в соответствующей привязке WSDL.</span><span class="sxs-lookup"><span data-stu-id="e410e-163">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>

- <span data-ttu-id="e410e-164">R2222: параметр действия `application/soap+xml`, если он присутствует в сообщении SOAP 1.2, должен соответствовать `wsa:Action`, если используется WS-Addressing 2004/08 или WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="e410e-164">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="e410e-165">Если привязка WS-Addressing отключена, а входящий запрос не содержит параметра действия, параметр `Action` сообщения считается неуказанным.</span><span class="sxs-lookup"><span data-stu-id="e410e-165">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>

## <a name="ws-addressing"></a><span data-ttu-id="e410e-166">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e410e-166">WS-Addressing</span></span>
<span data-ttu-id="e410e-167">WCF реализованы 3 версии WS-Addressing:</span><span class="sxs-lookup"><span data-stu-id="e410e-167">WCF implements 3 versions of WS-Addressing:</span></span>

- <span data-ttu-id="e410e-168">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="e410e-168">WS-Addressing 2004/08</span></span>

- <span data-ttu-id="e410e-169">W3C Web Services Addressing 1.0 Core (ADDR10-CORE) и SOAP Binding (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="e410e-169">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>

- <span data-ttu-id="e410e-170">WS-Addressing 1.0 ― метаданные</span><span class="sxs-lookup"><span data-stu-id="e410e-170">WS-Addressing 1.0 - Metadata</span></span>

### <a name="endpoint-references"></a><span data-ttu-id="e410e-171">Ссылки на конечные точки</span><span class="sxs-lookup"><span data-stu-id="e410e-171">Endpoint References</span></span>
<span data-ttu-id="e410e-172">Все версии протокола WS-Addressing, реализующий WCF использовать ссылки на конечные точки для описания конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e410e-172">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>

#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="e410e-173">Ссылки на конечные точки и версии WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e410e-173">Endpoint References and WS-Addressing Versions</span></span>
<span data-ttu-id="e410e-174">WCF реализует ряд протоколов инфраструктуры, использующих WS-Addressing и в частности `EndpointReference` элемент и `W3C.WsAddressing.EndpointReferenceType` класса (например, WS-ReliableMessaging WS-SecureConversation и WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="e410e-174">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="e410e-175">WCF поддерживает использование обеих версий WS-Addressing с другими протоколами инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="e410e-175">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="e410e-176">Конечные точки WCF поддерживают одну версию WS-Addressing на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e410e-176">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>

<span data-ttu-id="e410e-177">Для R3111 пространство имен для `EndpointReference` элемента или тип, используемый в сообщениях, обмен которыми осуществляется с конечной точкой WCF должна соответствовать версии WS-Addressing реализуемых этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="e410e-177">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>

<span data-ttu-id="e410e-178">Например, если конечная точка WCF реализует WS-ReliableMessaging `AcksTo` заголовок, возвращенный этой конечной точки внутри `CreateSequenceResponse` использует версию WS-Addressing, `EncodingBinding` элемент задает для этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e410e-178">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>

#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="e410e-179">Ссылки на конечные точки и метаданные</span><span class="sxs-lookup"><span data-stu-id="e410e-179">Endpoint References and Metadata</span></span>
<span data-ttu-id="e410e-180">В ряде сценариев требуется передача метаданных или ссылки на метаданные для определенной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e410e-180">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>

<span data-ttu-id="e410e-181">B3121: WCF используются механизмы, описанные в разделе 6, позволяющие включать метаданные для ссылки на конечные точки, по значению или по ссылке спецификации WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="e410e-181">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>

<span data-ttu-id="e410e-182">Рассмотрим ситуацию, где службы WCF требует проверки подлинности, с использованием маркера Security Assertions Markup Language (SAML), выданного издателем маркера в `http://sts.fabrikam123.com`.</span><span class="sxs-lookup"><span data-stu-id="e410e-182">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at `http://sts.fabrikam123.com`.</span></span> <span data-ttu-id="e410e-183">Конечная точка WCF описывает это требование проверки подлинности с помощью `sp:IssuedToken` утверждение с вложенным `sp:Issuer` утверждение, указывающий на издателя маркера.</span><span class="sxs-lookup"><span data-stu-id="e410e-183">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="e410e-184">Клиентское приложение, обращающееся к утверждению `sp:Issuer`, должно знать, как взаимодействовать с конечной точкой издателя маркера.</span><span class="sxs-lookup"><span data-stu-id="e410e-184">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="e410e-185">Клиенту требуются метаданные об издателе маркера.</span><span class="sxs-lookup"><span data-stu-id="e410e-185">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="e410e-186">Используя конечную точку расширения эталонных метаданных, определенную в MEX, WCF предоставляет ссылку на метаданные издателя токена.</span><span class="sxs-lookup"><span data-stu-id="e410e-186">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a><span data-ttu-id="e410e-187">Заголовки адресации сообщения</span><span class="sxs-lookup"><span data-stu-id="e410e-187">Message Addressing Headers</span></span>

#### <a name="message-headers"></a><span data-ttu-id="e410e-188">Заголовки сообщений</span><span class="sxs-lookup"><span data-stu-id="e410e-188">Message Headers</span></span>
<span data-ttu-id="e410e-189">Для обеих версий WS-Addressing, WCF использует следующие заголовки сообщения, как предписано в спецификациях `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, и `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="e410e-189">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>

<span data-ttu-id="e410e-190">B3211: Для всех версий WS-Addressing, WCF учитываются, но не по умолчанию, заголовки сообщения WS-Addressing `wsa:FaultTo` и `wsa:From`.</span><span class="sxs-lookup"><span data-stu-id="e410e-190">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>

<span data-ttu-id="e410e-191">Приложения, которые взаимодействуют с приложениями WCF можно добавить эти заголовки сообщений и WCF будет обрабатывать их соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e410e-191">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>

#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="e410e-192">Параметры и свойства ссылок</span><span class="sxs-lookup"><span data-stu-id="e410e-192">Reference Parameters and Properties</span></span>

<span data-ttu-id="e410e-193">WCF реализует обработку параметров ссылок на конечную точку и свойства ссылок согласно соответствующим спецификациями.</span><span class="sxs-lookup"><span data-stu-id="e410e-193">WCF implements processing of endpoint reference parameters and reference properties in accordance with respective specifications.</span></span>

<span data-ttu-id="e410e-194">B3221: Если настроена для использования WS-Addressing 2004/08, конечные точки WCF не различают обработку свойств ссылок и ссылочные параметры.</span><span class="sxs-lookup"><span data-stu-id="e410e-194">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>

### <a name="message-exchange-patterns"></a><span data-ttu-id="e410e-195">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="e410e-195">Message Exchange Patterns</span></span>
<span data-ttu-id="e410e-196">Последовательность сообщений, участвующих в вызове операции веб-службы называется *обмена сообщениями*.</span><span class="sxs-lookup"><span data-stu-id="e410e-196">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="e410e-197">WCF поддерживает односторонний обмен, запрос ответ и дуплексный шаблоны обмена.</span><span class="sxs-lookup"><span data-stu-id="e410e-197">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="e410e-198">В этом разделе поясняются требования WS-Addressing по обработке сообщений в зависимости от используемого шаблона обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e410e-198">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>

<span data-ttu-id="e410e-199">В этом разделе первое сообщение отправляется запрашивающей стороной и принимается отвечающей стороной.</span><span class="sxs-lookup"><span data-stu-id="e410e-199">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="e410e-200">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="e410e-200">One-Way Message</span></span>
<span data-ttu-id="e410e-201">После настройки конечной точки WCF для поддержки сообщений с помощью заданного `Action` в соответствии с односторонним обменом, конечная точка WCF соответствует указанным ниже поведениям и требованиям.</span><span class="sxs-lookup"><span data-stu-id="e410e-201">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="e410e-202">Если не указано иное, поведения и правила применимы для обеих версий WS-Addressing поддерживаются в WCF:</span><span class="sxs-lookup"><span data-stu-id="e410e-202">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="e410e-203">R3311: запрашивающая сторона должна включить `wsa:To`, `wsa:Action` и заголовки для всех ссылочных параметров, указанных ссылкой на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e410e-203">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="e410e-204">Если используется WS-Addressing 2004/08 и ссылкой на конечную точку заданы [reference properties], в сообщение также должны быть включены соответствующие заголовки.</span><span class="sxs-lookup"><span data-stu-id="e410e-204">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>

- <span data-ttu-id="e410e-205">B3312: запрашивающая сторона может включить заголовки `MessageID`, `ReplyTo` и `FaultTo`.</span><span class="sxs-lookup"><span data-stu-id="e410e-205">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="e410e-206">Инфраструктура принимающей стороны не учитывает их, и они передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="e410e-206">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>

- <span data-ttu-id="e410e-207">R3313: если используется HTTP и по ответному плечу HTTP не передается никакое сообщение, отвечающая сторона должна отправить ответ HTTP с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e410e-207">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>

     <span data-ttu-id="e410e-208">Если используется транспорт HTTP и в контракте операции объявлен односторонний обмен сообщениями, ответ HTTP все равно может использоваться для отправки инфраструктурных сообщений - например, протокол надежного обмена сообщениями может отправить сообщение `SequenceAcknowledgement` в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="e410e-208">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>

- <span data-ttu-id="e410e-209">B3314: Отвечающая сторона WCF не отправляет сообщение об ошибке в ответ на одностороннее сообщение.</span><span class="sxs-lookup"><span data-stu-id="e410e-209">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>

#### <a name="request-reply"></a><span data-ttu-id="e410e-210">Запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="e410e-210">Request-Reply</span></span>
<span data-ttu-id="e410e-211">После настройки конечной точки WCF для сообщения с заданной `Action` к шаблону запрос ответ, конечная точка WCF ниже поведениям и требованиям.</span><span class="sxs-lookup"><span data-stu-id="e410e-211">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="e410e-212">Если не указано иное, поведения и правила применимы для обеих версий WS-Addressing поддерживаются в WCF:</span><span class="sxs-lookup"><span data-stu-id="e410e-212">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="e410e-213">R3321: Запрашивающая сторона должна включить в запрос `wsa:To`, `wsa:Action`, `wsa:MessageID`и заголовки для всех ссылочных параметров или ссылки свойства (или оба) указанных ссылкой на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e410e-213">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>

- <span data-ttu-id="e410e-214">R3322: если используется WS-Addressing 2004/08, в запрос также должен быть включен параметр `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="e410e-214">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>

- <span data-ttu-id="e410e-215">R3323: Если используется WS-Addressing 1.0 и `ReplyTo` не присутствует в запросе, ссылку на конечную точку по умолчанию с помощью свойства [address], равным `http://www.w3.org/2005/08/addressing/anonymous` используется.</span><span class="sxs-lookup"><span data-stu-id="e410e-215">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to `http://www.w3.org/2005/08/addressing/anonymous` is used.</span></span>

- <span data-ttu-id="e410e-216">R3324: Запрашивающая сторона должна включить `wsa:To`, `wsa:Action`, и `wsa:RelatesTo` заголовки в ответном сообщении, а также заголовки для всех ссылочных параметров или ссылки свойства (или оба) определяемое `ReplyTo` ссылки на конечную точку в запрос.</span><span class="sxs-lookup"><span data-stu-id="e410e-216">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>

### <a name="web-services-addressing-faults"></a><span data-ttu-id="e410e-217">Ошибки Web Services Addressing</span><span class="sxs-lookup"><span data-stu-id="e410e-217">Web Services Addressing Faults</span></span>
<span data-ttu-id="e410e-218">R3411: WCF создает следующие ошибки, определенные в WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="e410e-218">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>

|<span data-ttu-id="e410e-219">Код</span><span class="sxs-lookup"><span data-stu-id="e410e-219">Code</span></span>|<span data-ttu-id="e410e-220">Причина</span><span class="sxs-lookup"><span data-stu-id="e410e-220">Cause</span></span>|
|----------|-----------|
|`wsa:DestinationUnreachable`|<span data-ttu-id="e410e-221">Поступило сообщение со значением `ReplyTo`, отличающимся от адреса ответа, установленного для данного канала; нет конечной точки, ожидающей передачи данных по адресу, указанному в заголовке «To».</span><span class="sxs-lookup"><span data-stu-id="e410e-221">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|
|`wsa:ActionNotSupported`|<span data-ttu-id="e410e-222">Каналы инфраструктуры или диспетчер, связанные с конечной точкой, не распознали действие, указанное в заголовке `Action`.</span><span class="sxs-lookup"><span data-stu-id="e410e-222">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|

<span data-ttu-id="e410e-223">R3412: WCF создает следующие ошибки, определенные в WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="e410e-223">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>

|<span data-ttu-id="e410e-224">Код</span><span class="sxs-lookup"><span data-stu-id="e410e-224">Code</span></span>|<span data-ttu-id="e410e-225">Причина</span><span class="sxs-lookup"><span data-stu-id="e410e-225">Cause</span></span>|
|----------|-----------|
|`wsa10:InvalidAddressingHeader`|<span data-ttu-id="e410e-226">Дублировать `wsa:To`, `wsa:ReplyTo`, `wsa:From` или `wsa:MessageID`.</span><span class="sxs-lookup"><span data-stu-id="e410e-226">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="e410e-227">Дублировать `wsa:RelatesTo` с тем же `RelationshipType`.</span><span class="sxs-lookup"><span data-stu-id="e410e-227">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|
|`wsa10:MessageAddressingHeaderRequired`|<span data-ttu-id="e410e-228">Отсутствует обязательный заголовок адресации.</span><span class="sxs-lookup"><span data-stu-id="e410e-228">The required Addressing header is missing.</span></span>|
|`wsa10:DestinationUnreachable`|<span data-ttu-id="e410e-229">Поступило сообщение со значением `ReplyTo`, отличающимся от адреса ответа, установленного для данного канала.</span><span class="sxs-lookup"><span data-stu-id="e410e-229">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="e410e-230">Нет конечной точки, ожидающей передачи данных по адресу, указанному в заголовке «To».</span><span class="sxs-lookup"><span data-stu-id="e410e-230">There is no endpoint listening at the address specified in the To header.</span></span>|
|`wsa10:ActionNotSupported`|<span data-ttu-id="e410e-231">Действие, указанное в заголовке `Action`, не распознано каналами инфраструктуры или диспетчером, связанным с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="e410e-231">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|
|`wsa10:EndpointUnavailable`|<span data-ttu-id="e410e-232">Канал надежного обмена сообщениями возвращает эту ошибку, указывающую на то, что конечная точка не обрабатывает последовательность на основании проверки заголовков адресов в сообщении `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e410e-232">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|

<span data-ttu-id="e410e-233">Код в предыдущих таблицах соответствует параметру `FaultCode` в SOAP 1.1 и параметру `SubCode` (с Code=Sender) в SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="e410e-233">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="e410e-234">Привязка WSDL 1.1 и утверждения WS-Policy</span><span class="sxs-lookup"><span data-stu-id="e410e-234">WSDL 1.1 Binding and WS-Policy Assertions</span></span>

#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="e410e-235">Указание использования WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e410e-235">Indicating Use of WS-Addressing</span></span>
<span data-ttu-id="e410e-236">WCF использует утверждения политики для указания определенной версии WS-Addressing, поддерживаемой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="e410e-236">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>

<span data-ttu-id="e410e-237">Следующее утверждение политики имеет субъект политики конечной точки [WS-PA] и указывает, что в сообщениях, отправляемых и принимаемых с конечной точки, должна использоваться спецификация WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="e410e-237">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsap:UsingAddressing />
```

<span data-ttu-id="e410e-238">Это утверждение политики дополняет спецификацию WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="e410e-238">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>

<span data-ttu-id="e410e-239">Следующее утверждение политики указывает, что в отправляемых и принимаемых сообщениях должна использоваться спецификация WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="e410e-239">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>

```xml
<wsam:Addressing/>
```

<span data-ttu-id="e410e-240">Следующее утверждение политики имеет субъект политики конечной точки [WS-PA] и указывает, что в сообщениях, отправляемых и принимаемых с конечной точки, должна использоваться спецификация WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="e410e-240">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsaw10:UsingAddressing />
```

<span data-ttu-id="e410e-241">Элемент `wsaw10:UsingAddressing` заимствован из [WS-Addressing-WSDL] и используется в контексте WS-Policy в соответствии с этой спецификацией, раздел 3.1.2.</span><span class="sxs-lookup"><span data-stu-id="e410e-241">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>

<span data-ttu-id="e410e-242">Использование Addressing не изменяет семантики привязок WSDL 1.1, SOAP 1.1 и SOAP 1.2 HTTP.</span><span class="sxs-lookup"><span data-stu-id="e410e-242">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="e410e-243">Например, если ожидается ответ на запрос, отправленный в конечную точку, использующую Addressing и привязку WSDL SOAP 1.x HTTP, ответ должен быть отправлен с помощью HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e410e-243">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>

<span data-ttu-id="e410e-244">Для ответов, передаваемых с помощью HTTP-ответа, используется следующее утверждение WS-AM.</span><span class="sxs-lookup"><span data-stu-id="e410e-244">For replies sent over the http response, the WS-AM assertion is:</span></span>

```xml
<wsam:AnonymousResponses/>
```

<span data-ttu-id="e410e-245">Полный код утверждения политики может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e410e-245">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="e410e-246">Тем не менее при использовании некоторых схем обмена сообщениями удобно использовать два независимых HTTP-соединения, установленные между запрашивающей и отвечающей сторонами. Например, это позволяет принимать незапрошенные односторонние сообщения, отправленные отвечающей стороной.</span><span class="sxs-lookup"><span data-stu-id="e410e-246">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>

<span data-ttu-id="e410e-247">WCF предоставляет возможность, по которому два базовых транспортных канала можно объединить в составной дуплексный канал, где один канал используется для входящих сообщений, а другой используется для вывода сообщений.</span><span class="sxs-lookup"><span data-stu-id="e410e-247">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="e410e-248">В случае транспорта HTTP составной дуплексный канал обеспечивает два встречных HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="e410e-248">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="e410e-249">Запрашивающая сторона использует одно соединение для отправки сообщений отвечающей стороне, а отвечающая сторона использует другой канал для отправки сообщений обратно запрашивающей стороне.</span><span class="sxs-lookup"><span data-stu-id="e410e-249">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>

<span data-ttu-id="e410e-250">Для ответов на отдельные запросы http используется следующее утверждение WS-AM.</span><span class="sxs-lookup"><span data-stu-id="e410e-250">For replies sent over separate http requests, the ws-am assertion is</span></span>

```xml
<wsam:NonAnonymousResponses/>
```

<span data-ttu-id="e410e-251">Полный код утверждения политики может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e410e-251">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="e410e-252">Использование следующего утверждения, содержащего субъект политики конечной точки [WS-PA], в конечных точках, в которых используются привязки WSDL 1.1 SOAP 1.x HTTP, требует двух отдельных встречных HTTP-соединений для передачи сообщений от запрашивающей стороны к отвечающей стороне и для передачи сообщений от отвечающей стороны к запрашивающей стороне соответственно.</span><span class="sxs-lookup"><span data-stu-id="e410e-252">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>

```xml
<cdp:CompositeDuplex/>
```

<span data-ttu-id="e410e-253">Предыдущий оператор определяет следующие требования к заголовку `wsa:ReplyTo` для сообщений запроса.</span><span class="sxs-lookup"><span data-stu-id="e410e-253">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>

- <span data-ttu-id="e410e-254">R3514: Сообщения запроса отправляются в конечную точку должны содержать `ReplyTo` заголовок с `[address]` свойства не равно `http://www.w3.org/2005/08/addressing/anonymous` Если эта конечная точка использует привязку WSDL 1.1 SOAP 1.x HTTP и вариант политики с `wsap10:UsingAddressing` или `wsap:UsingAddressing` утверждение в сочетании с `cdp:CompositeDuplex` подключен.</span><span class="sxs-lookup"><span data-stu-id="e410e-254">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>

- <span data-ttu-id="e410e-255">R3515: Сообщения запроса отправляются в конечную точку должны содержать `ReplyTo` заголовок с `[address]` равным `http://www.w3.org/2005/08/addressing/anonymous`, или нет `ReplyTo` заголовок вообще, если эта конечная точка использует привязку WSDL 1.1 SOAP 1.x HTTP и вариант политики с `wsap10:UsingAddressing` утверждение и нет `cdp:CompositeDuplex` присоединенного утверждения.</span><span class="sxs-lookup"><span data-stu-id="e410e-255">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous`, or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

- <span data-ttu-id="e410e-256">R3516: Сообщения запроса отправляются в конечную точку должны содержать `ReplyTo` заголовок с `[address]` равным `http://www.w3.org/2005/08/addressing/anonymous` Если эта конечная точка использует привязку WSDL 1.1 SOAP 1.x HTTP и вариант политики с `wsap:UsingAddressing` утверждения и не `cdp:CompositeDuplex`присоединенного утверждения.</span><span class="sxs-lookup"><span data-stu-id="e410e-256">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

<span data-ttu-id="e410e-257">Спецификация WS-Addressing языка WSDL пытается описать аналогичные привязки протокола путем введения элемента `<wsaw:Anonymous/>` с тремя текстовыми значениями (обязательный, необязательный и запрещен), указывающими требования к заголовку `wsa:ReplyTo` (раздел 3.2).</span><span class="sxs-lookup"><span data-stu-id="e410e-257">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="e410e-258">К сожалению, такое определение элемента плохо подходит в качестве утверждения в контексте спецификации WS-Policy, так как оно требует специфичных для домена расширений, поддерживающих пересечение альтернатив, использующих такой элемент в качестве утверждения.</span><span class="sxs-lookup"><span data-stu-id="e410e-258">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="e410e-259">Кроме того, такое определение элемента задает значение заголовка `ReplyTo` в противоположность поведению конечной точки в канале связи, что делает его специфичным для транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="e410e-259">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>

#### <a name="action-definition"></a><span data-ttu-id="e410e-260">Определение действия</span><span class="sxs-lookup"><span data-stu-id="e410e-260">Action Definition</span></span>
<span data-ttu-id="e410e-261">Спецификация WS-Addressing 2004/08 определяет атрибут `wsa:Action` для элементов `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`.</span><span class="sxs-lookup"><span data-stu-id="e410e-261">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="e410e-262">Привязка WS-Addressing 1.0 WSDL (WS-ADDR10-WSDL) определяет аналогичный атрибут, `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="e410e-262">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>

<span data-ttu-id="e410e-263">Единственное отличие между этими двумя атрибутами заключается в семантике шаблона действия по умолчанию, описанной в разделе 3.3.2 спецификации WS-ADDR и в разделе 4.4.4 спецификации WS-ADDR10-WSDL соответственно.</span><span class="sxs-lookup"><span data-stu-id="e410e-263">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>

<span data-ttu-id="e410e-264">Разумно иметь две конечные точки, использующих одинаковый `portType` (или контракт, в терминологии WCF), но с использованием разных версий WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="e410e-264">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="e410e-265">Однако с учетом того, что действие определяется параметром `portType` и не должно изменяться между конечными точками, реализующими `portType`, одновременная поддержка обоих шаблонов действия по умолчанию становится невозможной.</span><span class="sxs-lookup"><span data-stu-id="e410e-265">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>

<span data-ttu-id="e410e-266">Чтобы устранить это противоречие, WCF поддерживает одну версию `Action` атрибута.</span><span class="sxs-lookup"><span data-stu-id="e410e-266">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>

<span data-ttu-id="e410e-267">B3521: WCF использует `wsaw10:Action` атрибут `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` элементы, как определено в спецификации WS-ADDR10-WSDL, чтобы определить `Action` URI для соответствующих сообщений независимо от версии WS-Addressing, используемый конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="e410e-267">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>

#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="e410e-268">Использование ссылки на конечную точку внутри порта WSDL</span><span class="sxs-lookup"><span data-stu-id="e410e-268">Use Endpoint Reference Inside WSDL Port</span></span>
<span data-ttu-id="e410e-269">Раздел 4.1 спецификации WS-ADDR10-WSDL расширяет элемент `wsdl:port`, включая в него дочерний элемент `<wsa10:EndpointReference…/>` для описания конечной точки в терминах WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="e410e-269">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="e410e-270">WCF расширяет эту возможность на спецификацию WS-Addressing 2004/08, позволяя `<wsa:EndpointReference…/>` отображаться как дочерний элемент элемента `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="e410e-270">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>

- <span data-ttu-id="e410e-271">R3531: если к конечной точке прикреплена альтернативная политика с утверждением политики `<wsaw10:UsingAddressing/>`, соответствующий элемент`wsdl:port` может содержать дочерний элемент`<wsa10:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="e410e-271">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>

- <span data-ttu-id="e410e-272">R3532: Если `wsdl:port` содержит дочерний элемент `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` значение дочернего элемента должно соответствовать значению из `@address` того же уровня `wsdl:port` / `wsdl:location` элемент.</span><span class="sxs-lookup"><span data-stu-id="e410e-272">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

- <span data-ttu-id="e410e-273">R3533: если к конечной точке прикреплена альтернативная политика с утверждением политики `<wsap:UsingAddressing/>`, соответствующий элемент`wsdl:port` может содержать дочерний элемент`<wsa:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="e410e-273">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>

- <span data-ttu-id="e410e-274">R3534: Если `wsdl:port` содержит дочерний элемент `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` значение дочернего элемента должно соответствовать значению из `@address` того же уровня `wsdl:port` / `wsdl:location` элемент.</span><span class="sxs-lookup"><span data-stu-id="e410e-274">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="e410e-275">Сочетаемость с WS-Security</span><span class="sxs-lookup"><span data-stu-id="e410e-275">Composition with WS-Security</span></span>
<span data-ttu-id="e410e-276">В соответствии с разделами спецификаций WS-ADDR и WS-ADDR10, посвященными вопросам безопасности, все заголовки адресации сообщения рекомендуется подписывать совместно с телом сообщения, чтобы связать их вместе.</span><span class="sxs-lookup"><span data-stu-id="e410e-276">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>

<span data-ttu-id="e410e-277">Если для защиты целостности сообщения используется WS-Security, заголовки сообщения WS-Addressing, а также заголовки, связанные с параметрами или свойствами (или и тем, и другим) ссылки, должны быть подписаны совместно с телом сообщения.</span><span class="sxs-lookup"><span data-stu-id="e410e-277">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>

### <a name="examples"></a><span data-ttu-id="e410e-278">Примеры</span><span class="sxs-lookup"><span data-stu-id="e410e-278">Examples</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="e410e-279">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="e410e-279">One-Way Message</span></span>
<span data-ttu-id="e410e-280">В этом сценарии отправитель отправляет одностороннее сообщение принимающей стороне.</span><span class="sxs-lookup"><span data-stu-id="e410e-280">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="e410e-281">Используются SOAP 1.2, HTTP 1.1 и W3C WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="e410e-281">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="e410e-282">Структура сообщения запроса: заголовки сообщения содержат элементы `wsa10:To` и `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="e410e-282">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="e410e-283">Тело сообщения содержит специфичный элемент `<app:Ping>` из пространства имен приложения.</span><span class="sxs-lookup"><span data-stu-id="e410e-283">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>

<span data-ttu-id="e410e-284">Заголовки HTTP: Назначение в POST соответствует URI в `wsa10:To` элемент.</span><span class="sxs-lookup"><span data-stu-id="e410e-284">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>

<span data-ttu-id="e410e-285">Заголовок Content-Type имеет значение `application/soap+xml`, как требуется спецификацией SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="e410e-285">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="e410e-286">Присутствуют параметры `charset` и `action`.</span><span class="sxs-lookup"><span data-stu-id="e410e-286">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="e410e-287">Параметр `action` заголовка Content-Type соответствует значению заголовка сообщения `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="e410e-287">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>

```
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay 
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

<span data-ttu-id="e410e-288">Получающая сторона отвечает пустым ответом HTTP и состоянием 202.</span><span class="sxs-lookup"><span data-stu-id="e410e-288">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="e410e-289">Пример ответа HTTP:</span><span class="sxs-lookup"><span data-stu-id="e410e-289">An example of the HTTP response:</span></span>

```
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="e410e-290">Механизм оптимизации передачи сообщений SOAP</span><span class="sxs-lookup"><span data-stu-id="e410e-290">SOAP Message Transmission Optimization Mechanism</span></span>
<span data-ttu-id="e410e-291">В этом разделе описываются подробности реализации WCF для механизма HTTP SOAP MTOM.</span><span class="sxs-lookup"><span data-stu-id="e410e-291">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="e410e-292">Технология MTOM представляет собой механизм кодирования сообщений SOAP того же класса как кодировкой традиционных text/XML или WCF двоичное кодирование.</span><span class="sxs-lookup"><span data-stu-id="e410e-292">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="e410e-293">MTOM включает в себя следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="e410e-293">MTOM includes the following:</span></span>

- <span data-ttu-id="e410e-294">Кодировка XML и механизм упаковки, описываемый [XOP], который оптимизирует информационные элементы XML, содержащие двоичные данные в кодировке base64, в отдельные двоичные части.</span><span class="sxs-lookup"><span data-stu-id="e410e-294">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>

- <span data-ttu-id="e410e-295">Инкапсуляция MIME пакета XOP, которая сериализует набор сведений XML и каждую двоичную часть пакета XOP в отдельную часть MIME.</span><span class="sxs-lookup"><span data-stu-id="e410e-295">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>

- <span data-ttu-id="e410e-296">Кодирование MIME XOP, примененное к конверту SOAP 1.x.</span><span class="sxs-lookup"><span data-stu-id="e410e-296">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="e410e-297">Привязка транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="e410e-297">An HTTP transport binding.</span></span>

<span data-ttu-id="e410e-298">Это позволяет использовать механизм MTOM с транспортом HTTP с WCF.</span><span class="sxs-lookup"><span data-stu-id="e410e-298">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="e410e-299">Однако этот раздел посвящен HTTP.</span><span class="sxs-lookup"><span data-stu-id="e410e-299">However, in this topic we will focus on HTTP.</span></span>

<span data-ttu-id="e410e-300">Формат MTOM построен на основе большого количества спецификаций, охватывающих сам механизм MTOM, XOP и MIME.</span><span class="sxs-lookup"><span data-stu-id="e410e-300">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="e410e-301">Модульность этого набора спецификаций затрудняет реконструкцию точных требований к формату и семантике обработки.</span><span class="sxs-lookup"><span data-stu-id="e410e-301">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="e410e-302">В этом разделе описываются формат и требования к обработке для привязки MTOM HTTP.</span><span class="sxs-lookup"><span data-stu-id="e410e-302">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>

### <a name="mtom-message-encoding"></a><span data-ttu-id="e410e-303">Кодирование сообщений MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-303">MTOM Message Encoding</span></span>

#### <a name="generating-mtom-messages"></a><span data-ttu-id="e410e-304">Создание сообщений MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-304">Generating MTOM messages</span></span>
<span data-ttu-id="e410e-305">В спецификации [XOP], раздел 3.1, описывается процесс кодирования XML с информационными единицами элемента, содержащими base64-значения, в абстрактно определенный пакет XOP.</span><span class="sxs-lookup"><span data-stu-id="e410e-305">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>

<span data-ttu-id="e410e-306">Приведенная ниже последовательность этапов описывает специфичный для MTOM процесс кодирования.</span><span class="sxs-lookup"><span data-stu-id="e410e-306">The following sequence of steps describes the MTOM-specific encoding process:</span></span>

1. <span data-ttu-id="e410e-307">Убедитесь, что конверт SOAP содержит не информационного элемента с `[namespace name]` из `http://www.w3.org/2004/08/xop/include` и `[local name]` из `Include`.</span><span class="sxs-lookup"><span data-stu-id="e410e-307">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of `http://www.w3.org/2004/08/xop/include` and a `[local name]` of `Include`.</span></span>

2. <span data-ttu-id="e410e-308">Создайте пустой пакет MIME.</span><span class="sxs-lookup"><span data-stu-id="e410e-308">Create an empty MIME package.</span></span>

3. <span data-ttu-id="e410e-309">Определите в исходном наборе сведений XML информационные единицы элементов, подлежащие оптимизации.</span><span class="sxs-lookup"><span data-stu-id="e410e-309">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="e410e-310">Для элементов, которые требуется оптимизировать, символы, составляющие `[children]` информационной элемент должен быть в канонической форме `xs:base64Binary` (см. XSD-2, 3.2.16 base64Binary) и не может содержать любые символы-разделители, предшествующие, встраивая его, или вслед за содержимым, отличных от пробела.</span><span class="sxs-lookup"><span data-stu-id="e410e-310">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>

4. <span data-ttu-id="e410e-311">Создайте конверт XOP SOAP, являющийся копией исходного конверта SOAP, но в котором дочерние элементы всех информационных единиц элементов, определенных на предыдущем шаге, заменены информационной единицей элементов `xop:Include`, построенной следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e410e-311">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>

    1. <span data-ttu-id="e410e-312">Преобразуйте замененные символы в двоичные данные, обработав их как данные в кодировке base64.</span><span class="sxs-lookup"><span data-stu-id="e410e-312">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>

    2. <span data-ttu-id="e410e-313">Создайте уникальное значение заголовка Content-ID, удовлетворяющее требованиям R3133 и R3134.</span><span class="sxs-lookup"><span data-stu-id="e410e-313">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>

    3. <span data-ttu-id="e410e-314">Создайте заголовок Content-Transfer-Encoding MIME со значением binary.</span><span class="sxs-lookup"><span data-stu-id="e410e-314">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>

    4. <span data-ttu-id="e410e-315">Если оптимизируемая информационная единица элемента ([parent] вновь вставленной информационной единицы `xop:Include`) имеет информационную единицу атрибута `xmime:contentType`, создайте заголовок Content-Type MIME со значением атрибута `xmime:contentType`.</span><span class="sxs-lookup"><span data-stu-id="e410e-315">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>

    5. <span data-ttu-id="e410e-316">Создайте новую двоичную часть MIME с содержимым, образованным двоичными данными, декодированными из замененных символов, обработанных как base64, заголовка Content-ID из шага 4b, заголовка Content-Transfer-Encoding из шага 4c, заголовка Content-Type, если он создан в шаге 4d.</span><span class="sxs-lookup"><span data-stu-id="e410e-316">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>

    6. <span data-ttu-id="e410e-317">Добавьте атрибут `href` в элемент `xop:Include` со значением cid: uri, полученным из значения заголовка Content-ID, созданного на шаге 4b.</span><span class="sxs-lookup"><span data-stu-id="e410e-317">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="e410e-318">Удалить вложенные "\<" и «>», URL-адрес-escape-символов оставшиеся строки затем добавьте префикс `cid:`.</span><span class="sxs-lookup"><span data-stu-id="e410e-318">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="e410e-319">В соответствии с RFC1738 и RFC2396 в escape-последовательности должен преобразовываться указанный ниже минимальный набор символов.</span><span class="sxs-lookup"><span data-stu-id="e410e-319">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="e410e-320">Возможно преобразование в escape-символы и других символов.</span><span class="sxs-lookup"><span data-stu-id="e410e-320">Other characters can be escaped.</span></span>

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. <span data-ttu-id="e410e-321">Создайте корневую часть MIME с конвертом XOP SOAP из шага 4.</span><span class="sxs-lookup"><span data-stu-id="e410e-321">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>

6. <span data-ttu-id="e410e-322">Запишите заголовки HTTP, включая заголовок HTTP Content-Type.</span><span class="sxs-lookup"><span data-stu-id="e410e-322">Write the HTTP headers, including the HTTP Content-Type header.</span></span>

7. <span data-ttu-id="e410e-323">Запишите пакет MIME.</span><span class="sxs-lookup"><span data-stu-id="e410e-323">Write the MIME package.</span></span>

#### <a name="processing-mtom-messages"></a><span data-ttu-id="e410e-324">Обработка сообщений MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-324">Processing MTOM messages</span></span>
<span data-ttu-id="e410e-325">Обработка сообщения MTOM производится точно в обратном порядке по сравнению с процессом, описанном в предыдущем разделе «Создание сообщений MTOM».</span><span class="sxs-lookup"><span data-stu-id="e410e-325">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>

1. <span data-ttu-id="e410e-326">Убедитесь, что корневая часть MIME имеет Content-Type `application/xop+xml`.</span><span class="sxs-lookup"><span data-stu-id="e410e-326">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>

2. <span data-ttu-id="e410e-327">Постройте конверт SOAP, проанализировав корневую часть MIME пакета как документ XML.</span><span class="sxs-lookup"><span data-stu-id="e410e-327">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="e410e-328">Кодировка символов определяется параметром `charset` заголовка Content-Type корневой части MIME.</span><span class="sxs-lookup"><span data-stu-id="e410e-328">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>

3. <span data-ttu-id="e410e-329">Для каждой информационной единицы элементов в построенном конверте SOAP, которая имеет, как единственный член своего свойства [children], информационную единицу элемента `xop:Include`:</span><span class="sxs-lookup"><span data-stu-id="e410e-329">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>

    1. <span data-ttu-id="e410e-330">Удалите префикс `cid:` и выполните обратное преобразование из escape-представления всех escape-последовательностей универсального кода ресурса (URI) (RFC 2396) в значении атрибута `@href` элемента `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="e410e-330">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="e410e-331">Заключите получившуюся строку в "\<«, «>».</span><span class="sxs-lookup"><span data-stu-id="e410e-331">Enclose the result string in "\<", ">".</span></span>

    2. <span data-ttu-id="e410e-332">Найдите часть MIME в значении заголовка Content-ID, соответствующую строке, полученной на шаге 3a.</span><span class="sxs-lookup"><span data-stu-id="e410e-332">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>

    3. <span data-ttu-id="e410e-333">Замените информационную единицу элемента `xop:Include`, имеющуюся в свойстве `children` каждой единицы, информационными единицами символов, представляющими каноническую кодировку base64 (см. XSD-2, 3.2.16 base64Binary) тела сущности части MIME, указанной в шаге 3b (эффективно это означает, что надо заменить информационную единицу элемента `xop:Include` данными, восстановленными из части пакета).</span><span class="sxs-lookup"><span data-stu-id="e410e-333">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>

#### <a name="http-content-type-header"></a><span data-ttu-id="e410e-334">Заголовок HTTP Content-Type</span><span class="sxs-lookup"><span data-stu-id="e410e-334">HTTP Content-Type Header</span></span>
<span data-ttu-id="e410e-335">Ниже приведен список уточнений WCF для формата заголовка HTTP Content-Type сообщения SOAP 1.x с кодировкой MTOM производным от требованиям, перечисленным в самой спецификации MTOM и являются производными от MTOM и RFC 2387.</span><span class="sxs-lookup"><span data-stu-id="e410e-335">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>

- <span data-ttu-id="e410e-336">R4131: заголовок HTTP Content-Type должен иметь значение multipart/related (без учета регистра) с параметрами.</span><span class="sxs-lookup"><span data-stu-id="e410e-336">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="e410e-337">В именах параметров регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="e410e-337">Parameter names are case-insensitive.</span></span> <span data-ttu-id="e410e-338">Порядок параметров не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="e410e-338">Parameter order is not significant.</span></span>

- <span data-ttu-id="e410e-339">Полная форма Бэкуса-Наура (BNF) заголовка Content-Type для сообщений MIME указана в RFC 2045, раздел 5.1.</span><span class="sxs-lookup"><span data-stu-id="e410e-339">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>

- <span data-ttu-id="e410e-340">R4132: заголовок HTTP Content-Type должен иметь параметр type со значением `application/xop+xml`, заключенным в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e410e-340">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>

<span data-ttu-id="e410e-341">Хотя требование использовать двойные кавычки не являются прямыми в RFC 2387, текст обнаруживает, что все параметры типа носителя multipart/related весьма вероятно будут содержать зарезервированные символы, такие как "\@" или «/» и поэтому требует двойных кавычек Помечает.</span><span class="sxs-lookup"><span data-stu-id="e410e-341">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>

- <span data-ttu-id="e410e-342">R4133: заголовок HTTP Content-Type должен иметь параметр start со значением заголовка Content-ID части MIME, содержащей конверт SOAP 1.x, заключенным в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e410e-342">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="e410e-343">Если параметр start опущен, первая часть MIME должна содержать конверт SOAP 1.x.</span><span class="sxs-lookup"><span data-stu-id="e410e-343">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="e410e-344">R4134: заголовок HTTP Content-Type для сообщения с кодировкой SOAP 1.1 MTOM должен содержать параметр start-info со значением text/xml, заключенным в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e410e-344">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="e410e-345">R4135: заголовок HTTP Content-Type для сообщения с кодировкой SOAP 1.2 MTOM должен содержать параметр start-info со значением `application/soap+xml`, заключенным в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e410e-345">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="e410e-346">R4136: заголовок HTTP Content-Type для сообщения с кодировкой SOAP 1.x MTOM должен содержать параметр boundary со значением (заключенным в двойные кавычки), соответствующим границе MIME BNF, определенной в спецификации RFC 2046, раздел 5.1.1.</span><span class="sxs-lookup"><span data-stu-id="e410e-346">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>

    ```
    boundary := 0*69<bchars> bcharsnospace 
    bchars := bcharsnospace / " " 
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+" 
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     <span data-ttu-id="e410e-347">Примеры</span><span class="sxs-lookup"><span data-stu-id="e410e-347">Examples:</span></span>

     <span data-ttu-id="e410e-348">ПРАВИЛЬНО</span><span class="sxs-lookup"><span data-stu-id="e410e-348">CORRECT</span></span>

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     <span data-ttu-id="e410e-349">ПРАВИЛЬНО</span><span class="sxs-lookup"><span data-stu-id="e410e-349">CORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     <span data-ttu-id="e410e-350">НЕПРАВИЛЬНО</span><span class="sxs-lookup"><span data-stu-id="e410e-350">INCORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1" 
    ```

#### <a name="infoset-mime-part"></a><span data-ttu-id="e410e-351">Часть Infoset MIME</span><span class="sxs-lookup"><span data-stu-id="e410e-351">Infoset MIME Part</span></span>
<span data-ttu-id="e410e-352">Конверт SOAP 1.x инкапсулируется как корневая часть пакета XOP MIME и часто называется частью `infoset`.</span><span class="sxs-lookup"><span data-stu-id="e410e-352">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>

- <span data-ttu-id="e410e-353">R4141: конверт SOAP 1.x должен быть инкапсулирован как корневая часть пакета XOP MIME, называемая частью `infoset`, ссылка на которую содержится в заголовке HTTP Content-Type.</span><span class="sxs-lookup"><span data-stu-id="e410e-353">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>

- <span data-ttu-id="e410e-354">R4142: часть SOAP `Infoset` должна содержать следующие заголовки MIME: `Content-ID`, `Content-Transfer-Encoding` и `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="e410e-354">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>

<span data-ttu-id="e410e-355">Формат заголовка Content-ID определяется в RFC 2045 как</span><span class="sxs-lookup"><span data-stu-id="e410e-355">The format of the Content-ID header is defined by RFC 2045 as</span></span>

```
"Content-ID" ":" msg-id
```

<span data-ttu-id="e410e-356">где `msg-id` определяется в RFC 2822 (которая заменяет RFC 822, указанную в RFC 2045) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e410e-356">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

<span data-ttu-id="e410e-357">и фактически адрес электронной почты заключены в "\<" и «>».</span><span class="sxs-lookup"><span data-stu-id="e410e-357">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="e410e-358">Префикс и суффикс `[CFWS]` были добавлены в RFC 2822 для внесения комментариев и не должны использоваться, чтобы не нарушать совместимость.</span><span class="sxs-lookup"><span data-stu-id="e410e-358">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>

<span data-ttu-id="e410e-359">R4143: значение заголовка Content-ID для части Infoset MIME должно задаваться в соответствии с правилами для `msg-id` из RFC 2822 без частей с префиксом и суффиксом `[CFWS]`.</span><span class="sxs-lookup"><span data-stu-id="e410e-359">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>

<span data-ttu-id="e410e-360">Ряде реализаций MIME ослаблены требования для значения, заключенные в "\<" и «>» было адресом электронной почты и использовать `absoluteURI` стояло "\<", «>» Помимо адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e410e-360">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="e410e-361">Эта версия WCF использует значения заголовка Content-ID MIME в форме:</span><span class="sxs-lookup"><span data-stu-id="e410e-361">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>

```
Content-ID: <http://tempuri.org/0> 
```

<span data-ttu-id="e410e-362">R4144: процессоры MTOM должны воспринимать значения заголовка Content-ID, соответствующие следующему ослабленному требованию к `msg-id`.</span><span class="sxs-lookup"><span data-stu-id="e410e-362">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

<span data-ttu-id="e410e-363">В MIME (RFC 2045) предусмотрен заголовок Content-Transfer-Encoding для сообщения о кодировке содержимого части MIME.</span><span class="sxs-lookup"><span data-stu-id="e410e-363">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="e410e-364">По умолчанию для Content-Transfer-Encoding задано значение 7-bit, которое не подходит для большинства сообщений SOAP, поэтому для расширения совместимости требуется заголовок Content-Transfer-Encoding:</span><span class="sxs-lookup"><span data-stu-id="e410e-364">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>

- <span data-ttu-id="e410e-365">R4145: часть SOAP Infoset должна содержать заголовок Content-Transfer-Encoding.</span><span class="sxs-lookup"><span data-stu-id="e410e-365">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>

- <span data-ttu-id="e410e-366">R4146: если для конверта SOAP принята кодировка символов UTF-8, значение заголовка Content-Transfer-Encoding должно быть 8-bit.</span><span class="sxs-lookup"><span data-stu-id="e410e-366">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>

- <span data-ttu-id="e410e-367">R4147: если для конверта SOAP принята кодировка символов UTF-16, значение заголовка Content-Transfer-Encoding должно быть binary.</span><span class="sxs-lookup"><span data-stu-id="e410e-367">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>

- <span data-ttu-id="e410e-368">В соответствии с [XOP], раздел 5,</span><span class="sxs-lookup"><span data-stu-id="e410e-368">According to [XOP] section 5,</span></span>

- <span data-ttu-id="e410e-369">R4148: Часть SOAP1.1 Infoset должна содержать заголовок Content-Type с типом мультимедиа application/xop + xml и параметрами type = «text/xml» и charset</span><span class="sxs-lookup"><span data-stu-id="e410e-369">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- <span data-ttu-id="e410e-370">R4149: Часть SOAP 1.2 Infoset должна содержать заголовок Content-Type с типом мультимедиа `application/xop+xml` и параметрами type =»`application/soap+xml`"и `charset`.</span><span class="sxs-lookup"><span data-stu-id="e410e-370">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     <span data-ttu-id="e410e-371">Хотя в XOP параметр `charset` для `application/xop+xml` определяется как необязательный, он необходим для совместимости, аналогично требованию BP 1.1 к параметру `charset` для типа носителя `text/xml`.</span><span class="sxs-lookup"><span data-stu-id="e410e-371">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>

- <span data-ttu-id="e410e-372">R41410: в заголовке Content-Type части SOAP 1.x Infoset должны присутствовать параметры `type` и `charset`.</span><span class="sxs-lookup"><span data-stu-id="e410e-372">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>

#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="e410e-373">Поддержка MTOM конечной точкой WCF</span><span class="sxs-lookup"><span data-stu-id="e410e-373">WCF Endpoint Support for MTOM</span></span>
<span data-ttu-id="e410e-374">Целью механизма MTOM является кодирование сообщения SOAP для оптимизации данных с кодировкой base64.</span><span class="sxs-lookup"><span data-stu-id="e410e-374">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="e410e-375">Ниже приведен список ограничений.</span><span class="sxs-lookup"><span data-stu-id="e410e-375">The following is a list of constraints:</span></span>

- <span data-ttu-id="e410e-376">R4151: любая информационная единица элемента, содержащая данные в кодировке base64, может быть оптимизирована.</span><span class="sxs-lookup"><span data-stu-id="e410e-376">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>

- <span data-ttu-id="e410e-377">B4152: WCF оптимизирует информационными единицами элемента, которые содержат данные в кодировке base64 и превышать в длину 1024 байта.</span><span class="sxs-lookup"><span data-stu-id="e410e-377">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>

<span data-ttu-id="e410e-378">Конечную точку WCF, настроены для использования MTOM всегда будут отправлять сообщения с кодировкой MTOM.</span><span class="sxs-lookup"><span data-stu-id="e410e-378">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="e410e-379">Даже если ни одна из частей не удовлетворяет требуемым критериям, сообщение все равно является MTOM-кодированным (сериализованным в виде пакета MIME с единственной частью MIME, содержащей конверт SOAP).</span><span class="sxs-lookup"><span data-stu-id="e410e-379">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>

### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="e410e-380">Утверждение WS-Policy для MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-380">WS-Policy Assertion for MTOM</span></span>
<span data-ttu-id="e410e-381">WCF использует следующее утверждение политики для указания использования MTOM конечной точкой:</span><span class="sxs-lookup"><span data-stu-id="e410e-381">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- <span data-ttu-id="e410e-382">R4211: предыдущее утверждение политики содержит субъект политики конечной точки и указывает, что все сообщения, отправляемые на конечную точку и получаемые от нее, должны быть оптимизированы с помощью MTOM.</span><span class="sxs-lookup"><span data-stu-id="e410e-382">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>

- <span data-ttu-id="e410e-383">B4212: Если задана оптимизация MTOM, конечную точку WCF добавляет утверждение политики MTOM в политику, присоединенную к соответствующей `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="e410e-383">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="e410e-384">Сочетаемость с WS-Security</span><span class="sxs-lookup"><span data-stu-id="e410e-384">Composition with WS-Security</span></span>
<span data-ttu-id="e410e-385">MTOM представляет собой механизм кодирования, которая похожа на `text/xml` и двоичными файлами XML WCF.</span><span class="sxs-lookup"><span data-stu-id="e410e-385">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="e410e-386">MTOM обеспечивает естественную сочетаемость с протоколом WS-Security и другими протоколами WS-\*: сообщение, защищенное с помощью протокола WS-Security, может быть оптимизировано с помощью MTOM.</span><span class="sxs-lookup"><span data-stu-id="e410e-386">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>

### <a name="examples"></a><span data-ttu-id="e410e-387">Примеры</span><span class="sxs-lookup"><span data-stu-id="e410e-387">Examples</span></span>

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="e410e-388">Сообщение WCF SOAP 1.1, закодированное с помощью MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-388">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>

```
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="e410e-389">Безопасное сообщение WCF SOAP 1.2, закодированное с помощью MTOM</span><span class="sxs-lookup"><span data-stu-id="e410e-389">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>
<span data-ttu-id="e410e-390">В этом примере с помощью MTOM и SOAP 1.2 кодируется сообщение, защищенное с помощью протокола WS-Security.</span><span class="sxs-lookup"><span data-stu-id="e410e-390">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="e410e-391">Двоичные части, указанные для кодирования, являются содержимым элементов `BinarySecurityToken`, `CipherValue` элемента `EncryptedData`, соответствующих зашифрованной подписи и зашифрованному телу.</span><span class="sxs-lookup"><span data-stu-id="e410e-391">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="e410e-392">Обратите внимание, что `CipherValue` из `EncryptedKey` не указан для оптимизации с WCF, так как его длина меньше 1024 байт.</span><span class="sxs-lookup"><span data-stu-id="e410e-392">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>

```
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml"; 
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```