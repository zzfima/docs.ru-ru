---
title: "&lt;webMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;webMessageEncoding&gt;
Позволяет читать и записывать сообщения, кодированные в формате обычного XML\-текста и JSON \(JavaScript Object Notation\), и необработанное двоичное содержимое при использовании в привязке [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Синтаксис  
  
```  
  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding=”UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`maxReadPoolSize`|Количество сообщений, которые можно читать одновременно, не выделяя памяти для новых обработчиков чтения.  Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.  Значение по умолчанию \- 64 обработчика чтения для каждого из внутренних кодировщиков \(простой текст, JSON, двоичное содержимое\).<br /><br /> Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества входящих сообщений, позволяя использовать уже созданные обработчики чтения из пула, а не создавать новые.|  
|`maxWritePoolSize`|Количество сообщений, которые можно отправить одновременно, не выделяя памяти для новых обработчиков записи.  Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.  Значение по умолчанию \- 16 обработчиков записи для каждого из внутренних кодировщиков \(простой текст, JSON, двоичное содержимое\).<br /><br /> Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества исходящих сообщений, позволяя использовать уже созданные обработчики записи из пула, а не создавать новые.|  
|`writeEncoding`|Задает кодировку, используемую при отправке сообщений через привязку.  Допустимые значения:<br /><br /> -   UnicodeFffeTextEncoding: кодировка Юникод \(обратный порядок байтов\).<br />-   Utf16TextEncoding: кодировка Юникод.<br />-   Utf8TextEncoding: 8\-разрядная кодировка.<br /><br /> Значение по умолчанию \- Utf8TextEncoding.  Это атрибут типа <xref:System.Text.Encoding>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Кодирование — это процесс преобразования сообщения в последовательность байтов.  Декодирование представляет собой обратный процесс.  Эти процессы требуют определения кодировки символов.  
  
 Элемент `webMessageEncoding` работает путем делегирования набору внутренних кодировщиков обработки кодировок XML \(в формате обычного текста\), JSON и двоичных данных.  Делегирование выполняется с помощью составного кодировщика сообщений.  
  
 Этот элемент привязки и его составной кодировщик используются для управления кодировкой в тех сценариях, где не применяется обмен сообщениями по протоколу SOAP, используемый элементом `webHttpBinding`.  К таким сценариям относятся: Plain Old XML \(POX\), REST \(Representational State Transfer\), RSS \(Really Simple Syndication\), синдикация Atom и AJAX \(Asynchronous JavaScript and XML\).  Составной кодировщик сообщений не поддерживает SOAP и WS\-Addressing.  
  
 В элементе привязки можно задать кодировку записи с помощью атрибута `writeEncoding`.  Предоставленное значение <xref:System.Text.Encoding> задает поведение при записи для форматов JSON и XML в текстовом виде.  Для чтения поддерживается любая допустимая кодировка сообщений и кодировка текста.  
  
 Атрибуты `maxReadPoolSize` и `maxWritePoolSize` также могут использоваться для установки максимального количества выделяемых обработчиков чтения и записи соответственно.  По умолчанию выделяется 64 обработчика чтения и 16 обработчиков записи.  
  
 Стандартные ограничения по сложности также задаются элементом [\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md), чтобы обеспечить защиту от атак типа «отказ в обслуживании» \(DoS\), которые пытаются использовать сложность сообщения, чтобы перегрузить ресурсы обработки конечной точки.  
  
## Пример  
  
```  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding=”utf-8”   
/>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>   
 [Message Encoding](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Выбор кодировщика сообщений](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)