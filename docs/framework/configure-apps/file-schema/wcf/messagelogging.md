---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: f54028489ec5aa34ae38115d7a582b01b9da92f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931417"
---
# <a name="messagelogging"></a><span data-ttu-id="2170f-101">\<Мессажелоггинг ></span><span class="sxs-lookup"><span data-stu-id="2170f-101">\<messageLogging></span></span>
<span data-ttu-id="2170f-102">Данный элемент определяет параметры ведения журнала сообщений для Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2170f-102">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="2170f-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2170f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2170f-104">\<Диагностические ></span><span class="sxs-lookup"><span data-stu-id="2170f-104">\<diagnostic></span></span>  
<span data-ttu-id="2170f-105">\<Мессажелоггинг ></span><span class="sxs-lookup"><span data-stu-id="2170f-105">\<messageLogging></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2170f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2170f-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2170f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2170f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2170f-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2170f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2170f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2170f-109">Attributes</span></span>  
  
|<span data-ttu-id="2170f-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2170f-110">Attribute</span></span>|<span data-ttu-id="2170f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2170f-111">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="2170f-112">Логическое значение, указывающее, заносится ли в журнал сообщение целиком (тело и заголовок сообщения).</span><span class="sxs-lookup"><span data-stu-id="2170f-112">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="2170f-113">Значением по умолчанию является `false`, означающее, что в журнал заносится только заголовок сообщения.</span><span class="sxs-lookup"><span data-stu-id="2170f-113">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="2170f-114">Действие этого параметра распространяется на все уровни ведения журнала сообщений (службы, транспорта и неправильных сообщений).</span><span class="sxs-lookup"><span data-stu-id="2170f-114">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="2170f-115">Логическое значение, указывающее, заносятся ли в журнал неправильные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2170f-115">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="2170f-116">Такие сообщения не учитываются в значении `maxMessagesToLog`.</span><span class="sxs-lookup"><span data-stu-id="2170f-116">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="2170f-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2170f-117">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="2170f-118">Логическое значение, указывающее, трассируются ли сообщения на уровне службы (перед шифрованием и преобразованиями, связанными с транспортом).</span><span class="sxs-lookup"><span data-stu-id="2170f-118">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="2170f-119">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2170f-119">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="2170f-120">Логическое значение, указывающее, трассируются ли сообщения на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="2170f-120">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="2170f-121">Применяются все фильтры, указанные в файле конфигурации, и трассируются только те сообщения, которые соответствуют данным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="2170f-121">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="2170f-122">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2170f-122">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="2170f-123">Положительное целое число, указывающее максимальное количество сообщений для внесения в журнал.</span><span class="sxs-lookup"><span data-stu-id="2170f-123">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="2170f-124">Значение по умолчанию — 1000.</span><span class="sxs-lookup"><span data-stu-id="2170f-124">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="2170f-125">Положительное целое число, указывающее максимальный размер сообщения для внесения в журнал (в байтах).</span><span class="sxs-lookup"><span data-stu-id="2170f-125">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="2170f-126">Сообщения, размер которых превышает данное ограничение, в журнал не вносятся.</span><span class="sxs-lookup"><span data-stu-id="2170f-126">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="2170f-127">Действие этого параметра распространяется на все уровни трассировки.</span><span class="sxs-lookup"><span data-stu-id="2170f-127">This setting affects all trace levels.</span></span> <span data-ttu-id="2170f-128">Значение по умолчанию - 262 144 (0x4000).</span><span class="sxs-lookup"><span data-stu-id="2170f-128">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2170f-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2170f-129">Child Elements</span></span>  
  
|<span data-ttu-id="2170f-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="2170f-130">Element</span></span>|<span data-ttu-id="2170f-131">Описание</span><span class="sxs-lookup"><span data-stu-id="2170f-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2170f-132">фильтры</span><span class="sxs-lookup"><span data-stu-id="2170f-132">filters</span></span>|<span data-ttu-id="2170f-133">Элемент `filters` содержит коллекцию фильтров XPath.</span><span class="sxs-lookup"><span data-stu-id="2170f-133">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="2170f-134">Если включена регистрация сообщений на уровне транспорта (то есть атрибуту `logMessagesAtTransportLevel` присвоено значение `true`), в журнал заносятся только те сообщения, которые соответствуют фильтрам.</span><span class="sxs-lookup"><span data-stu-id="2170f-134">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="2170f-135">Фильтры применяются только на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="2170f-135">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="2170f-136">Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.</span><span class="sxs-lookup"><span data-stu-id="2170f-136">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="2170f-137">Единственным атрибутом элемента `filter` является XpathFilter.</span><span class="sxs-lookup"><span data-stu-id="2170f-137">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="2170f-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2170f-138">Parent Elements</span></span>  
  
|<span data-ttu-id="2170f-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="2170f-139">Element</span></span>|<span data-ttu-id="2170f-140">Описание</span><span class="sxs-lookup"><span data-stu-id="2170f-140">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2170f-141">диагностика</span><span class="sxs-lookup"><span data-stu-id="2170f-141">diagnostics</span></span>|<span data-ttu-id="2170f-142">Определяет параметры WCF для проверки во время выполнения и управления администратором.</span><span class="sxs-lookup"><span data-stu-id="2170f-142">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2170f-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="2170f-143">Remarks</span></span>  
 <span data-ttu-id="2170f-144">Сообщения вносятся в журнал на трех различных уровнях в стеке: сообщения уровня службы, транспорта и неправильные сообщения.</span><span class="sxs-lookup"><span data-stu-id="2170f-144">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="2170f-145">Активация каждого уровня может происходить отдельно.</span><span class="sxs-lookup"><span data-stu-id="2170f-145">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="2170f-146">Фильтры XPath можно добавлять для внесения в журнал отдельных сообщений уровней транспорта и службы.</span><span class="sxs-lookup"><span data-stu-id="2170f-146">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="2170f-147">Если не определено ни одного фильтра, в журнал вносятся все сообщения.</span><span class="sxs-lookup"><span data-stu-id="2170f-147">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="2170f-148">Фильтры применяются только к заголовкам сообщений.</span><span class="sxs-lookup"><span data-stu-id="2170f-148">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="2170f-149">Текст сообщения не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="2170f-149">The body is ignored.</span></span> <span data-ttu-id="2170f-150">WCF игнорирует тело сообщения для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="2170f-150">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="2170f-151">Если требуется применить фильтрацию по содержимому текста сообщения, можно создать пользовательский прослушиватель с фильтром, который будет выполнять эту задачу.</span><span class="sxs-lookup"><span data-stu-id="2170f-151">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="2170f-152">Чтобы включить трассировку сообщений, необходимо создать прослушиватель трассировки.</span><span class="sxs-lookup"><span data-stu-id="2170f-152">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="2170f-153">Сам прослушиватель может быть любым прослушивателем, который работает с архитектурой трассировки <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="2170f-153">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="2170f-154">В следующем примере показано создание подобного прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="2170f-154">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a><span data-ttu-id="2170f-155">Пример</span><span class="sxs-lookup"><span data-stu-id="2170f-155">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="2170f-156">См. также</span><span class="sxs-lookup"><span data-stu-id="2170f-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="2170f-157">Настройка ведения журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="2170f-157">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
