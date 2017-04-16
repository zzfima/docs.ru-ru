---
title: "&lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84179d77-825d-44b9-895a-ab08e7aa044d
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;webHttpBinding&gt;
Определяет элемент привязки, используемый при настройке конечных точек для веб\-службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые отвечают на запросы HTTP вместо сообщений протокола SOAP.  
  
## Синтаксис  
  
```  
  
<webHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxBufferSize="integer"  
        maxReceivedMessageSize="Integer"  
        name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
        useDefaultWebProxy="Boolean">  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        <security mode="None/Transport/TransportCredentialOnly">  
            <transport clientCredentialType =   
                 "Basic/Certificate/Digest/None/Ntlm/Windows"  
                  proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                  realm="string" />  
        </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</webHttpBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|allowCookies|Логическое значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.  Значение по умолчанию – false.<br /><br /> Это свойство можно использовать при взаимодействии с веб\-службами ASMX, которые используют файлы Cookie.  В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.|  
|bypassProxyOnLocal|Логическое значение, определяющее, будет ли выполняться обход прокси\-сервера для локальных адресов.  Значение по умолчанию — `false`.|  
|closeTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|hostnameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов \(URI\).  Это атрибут типа <xref:System.ServiceModel.HostnameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов \(URI\).  Значение по умолчанию — <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|  
|maxBufferPoolSize|Целое число, задающее максимальный размер буферного пула для этой привязки.  Значение по умолчанию \- 524 288 байт \(512 \* 1024\).  Многие элементы Windows Communication Foundation \(WCF\) используют буферы.  При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.  Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.  Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|maxBufferSize|Целое число, задающее максимальный объем памяти, выделяемый для диспетчера буферов сообщений, получающих сообщения из канала.  Значение по умолчанию \- 524 288 \(0x80 000\) байт.|  
|maxReceivedMessageSize|Положительное целое число, задающее, в байтах, максимальный размер сообщения \(включая заголовки\), которое можно получить по каналу, настроенному с использованием этой привязки.  Отправитель сообщения, которое превысит это ограничение, получит ошибку.  Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.  Значение по умолчанию — 65536. **Note:**  Увеличения только этого значения в режиме совместимости ASP.NET недостаточно.  Также необходимо увеличить значение `httpRuntime` \(см. в разделе [Элемент httpRuntime \(схема параметров ASP.NET\)](http://msdn.microsoft.com/ru-ru/e9b81350-8aaf-47cc-9843-5f7d0c59f369)\).|  
|имя|Строка, содержащая имя конфигурации привязки.  Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|proxyAddress|Универсальный код ресурса \(URI\), задающий адрес прокси\-сервера HTTP.  Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.  Значение по умолчанию — `null`.|  
|receiveTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|sendTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|transferMode.|Значение <xref:System.ServiceModel.TransferMode>, которое определяет, используется ли службой, настроенной с помощью привязки, потоковый или буферный режим \(или оба режима\) передачи сообщений.  Значение по умолчанию — `Buffered`.|  
|useDefaultWebProxy|Логическое значение, определяющее, должен ли использоваться автоматически настроенный системный прокси\-сервер HTTP.  Значение по умолчанию — `true`.|  
|writeEncoding|Задает кодировку, используемую в тексте сообщений.  Допустимы следующие значения:<br /><br /> UnicodeFffeTextEncoding: кодировка Юникод \(обратный порядок байтов\).<br /><br /> Utf16TextEncoding: 16\-разрядная кодировка.<br /><br /> Utf8TextEncoding: 8\-разрядная кодировка.<br /><br /> Значение по умолчанию \- Utf8TextEncoding.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений POX, которые могут обрабатываться конечными точками, настроенными с помощью этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|Определяет параметры безопасности привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.WebHttpSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязки\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## Заметки  
 Модель веб\-программирования [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] позволяет разработчикам предоставлять веб\-службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] с помощью запросов протокола HTTP, в которых используется стиль «Plain Old XML» \(POX\) вместо обмена сообщениями на основе протокола SOAP.  Чтобы клиенты могли взаимодействовать со службой, используя запросы протокола HTTP, конечная точка службы должна быть настроена с использованием привязки [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), к которой подключено поведение \<WebHttpBehavior\>.  
  
 Поддержка в [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] механизма синдикации и интеграции технологии ASP.AJAX строится на базе модели веб\-программирования.  Дополнительные сведения о модели см. в разделе [Модель веб\-программирования HTTP WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
## См. также  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>   
 [Модель веб\-программирования HTTP WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)