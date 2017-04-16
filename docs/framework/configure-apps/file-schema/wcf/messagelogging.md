---
title: "&lt;messageLogging&gt;&lt;/messageLogging&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;messageLogging&gt;&lt;/messageLogging&gt;
Данный элемент определяет параметры ведения журнала сообщений для Windows Communication Foundation (WCF).  
  
 \<system.ServiceModel>  
<>\>  
<>\>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<system.serviceModel>  
   <diagnostics>  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
                    maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
                            <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`logEntireMessage`|Логическое значение, указывающее, заносится ли в журнал сообщение целиком (тело и заголовок сообщения). Значением по умолчанию является `false`, означающее, что в журнал заносится только заголовок сообщения. Действие этого параметра распространяется на все уровни ведения журнала сообщений (службы, транспорта и неправильных сообщений).|  
|`logMalformedMessages`|Логическое значение, указывающее, заносятся ли в журнал неправильные сообщения. Такие сообщения не учитываются в значении `maxMessagesToLog`. Значение по умолчанию — `false`.|  
|`logMessagesAtServiceLevel`|Логическое значение, указывающее, трассируются ли сообщения на уровне службы (перед шифрованием и преобразованиями, связанными с транспортом). Значение по умолчанию — `false`.|  
|`logMessagesAtTransportLevel`|Логическое значение, указывающее, трассируются ли сообщения на уровне транспорта. Применяются все фильтры, указанные в файле конфигурации, и трассируются только те сообщения, которые соответствуют данным фильтрам. Значение по умолчанию — `false`.|  
|`maxMessagesToLog`|Положительное целое число, указывающее максимальное количество сообщений для внесения в журнал. Значение по умолчанию — 1000.|  
|`maxSizeOfMessageToLog`|Положительное целое число, указывающее максимальный размер сообщения для внесения в журнал (в байтах). Сообщения, размер которых превышает данное ограничение, в журнал не вносятся. Действие этого параметра распространяется на все уровни трассировки. Значение по умолчанию - 262 144 (0x4000).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|фильтры|Элемент `filters` содержит коллекцию фильтров XPath. Если включена регистрация сообщений на уровне транспорта (то есть атрибуту `logMessagesAtTransportLevel` присвоено значение `true`), в журнал заносятся только те сообщения, которые соответствуют фильтрам.<br /><br /> Фильтры применяются только на уровне транспорта. Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.<br /><br /> Единственным атрибутом элемента `filter` является XpathFilter.<br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|диагностика|Определяет параметры WCF для проверки во время выполнения и управления администратором.|  
  
## <a name="remarks"></a>Примечания  
 Сообщения вносятся в журнал на трех различных уровнях в стеке: сообщения уровня службы, транспорта и неправильные сообщения. Активация каждого уровня может происходить отдельно.  
  
 Фильтры XPath можно добавлять для внесения в журнал отдельных сообщений уровней транспорта и службы. Если не определено ни одного фильтра, в журнал вносятся все сообщения. Фильтры применяются только к заголовкам сообщений. Текст сообщения не обрабатывается. WCF игнорирует тело сообщения для повышения производительности. Если требуется применить фильтрацию по содержимому текста сообщения, можно создать пользовательский прослушиватель с фильтром, который будет выполнять эту задачу.  
  
 Чтобы включить трассировку сообщений, необходимо создать прослушиватель трассировки. Сам прослушиватель может быть любым прослушивателем, который работает с <xref:System.Diagnostics> архитектурой трассировки. В следующем примере показано создание подобного прослушивателя.  
  
```  
<system.diagnostics>  
    <sources>  
          <source name="System.ServiceModel" switchValue="Verbose">  
              <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="ServiceModel Listener" traceOutputOptions="None" />  
               </listeners>  
        </source>  
            <source name="System.ServiceModel.MessageLogging">  
                <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="MessageLogging Listener" traceOutputOptions="None"/>  
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
  
## <a name="example"></a>Пример  
  
```  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>   
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>   
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>   
 [Настройка ведения журнала сообщений](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)