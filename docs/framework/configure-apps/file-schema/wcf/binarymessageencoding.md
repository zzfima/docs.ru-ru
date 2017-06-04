---
title: "&lt;binaryMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;binaryMessageEncoding&gt;
Определяет кодировщик двоичных сообщений, кодирующий сообщения Windows Communication Foundation \(WCF\) в двоичном формате в сети.  
  
## Синтаксис  
  
```  
  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10” />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|maxReadPoolSize|Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.  Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.  Значение по умолчанию — 64.|  
|maxSessionSize|Положительное целое число, задающее размер буфера, используемого для кодирования \(в байтах\).  Буфер большего размера повышает скорость кодирования за счет размера рабочего набора.  Значение по умолчанию — 2048.|  
|maxWritePoolSize|Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.  Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.  Значение по умолчанию — 16.|  
|messageVersion|Определяет используемые или ожидаемые версии сообщения SOAP и WS\-Addressing.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Кодирование — это процесс преобразования сообщения в последовательность байтов.  Декодирование представляет собой обратный процесс.  В Windows Communication Foundation \(WCF\) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.  
  
 Элемент `binaryMessageEncoding` указывает двоичный формат .NET для XML и содержит параметры, задающие кодировку символов и версию SOAP и WS\-Addressing для использования.  Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation \(WCF\) в двоичном формате в сети.  Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS\-\*.  
  
## Пример  
  
```  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>   
 [Message Encoding](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Выбор кодировщика сообщений](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)