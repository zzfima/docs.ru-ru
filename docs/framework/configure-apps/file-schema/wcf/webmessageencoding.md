---
title: '&lt;webMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e6257721f8b85296d4da28cc036c946f6357c11b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebmessageencodinggt"></a>&lt;webMessageEncoding&gt;
Позволяет читать и записывать сообщения, кодированные в формате обычного XML-текста и JSON (JavaScript Object Notation), и необработанное двоичное содержимое при использовании в привязке [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<webMessageEncoding >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`maxReadPoolSize`|Количество сообщений, которые можно читать одновременно, не выделяя памяти для новых обработчиков чтения. Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора. Значение по умолчанию - 64 обработчика чтения для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).<br /><br /> Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества входящих сообщений, позволяя использовать уже созданные обработчики чтения из пула, а не создавать новые.|  
|`maxWritePoolSize`|Количество сообщений, которые можно отправить одновременно, не выделяя памяти для новых обработчиков записи. Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора. Значение по умолчанию - 16 обработчиков записи для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).<br /><br /> Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества исходящих сообщений, позволяя использовать уже созданные обработчики записи из пула, а не создавать новые.|  
|`writeEncoding`|Задает кодировку, используемую при отправке сообщений через привязку. Допустимые значения:<br /><br /> -UnicodeFffeTextEncoding: Big Endian кодировку Юникод.<br />-Utf16TextEncoding: Кодировка Юникод.<br />-Utf8TextEncoding: 8-разрядная кодировка.<br /><br /> Значение по умолчанию - Utf8TextEncoding. Это атрибут типа <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Кодирование — это процесс преобразования сообщения в последовательность байтов. Декодирование представляет собой обратный процесс. Эти процессы требуют определения кодировки символов.  
  
 Элемент `webMessageEncoding` работает путем делегирования набору внутренних кодировщиков обработки кодировок XML (в формате обычного текста), JSON и двоичных данных. Делегирование выполняется с помощью составного кодировщика сообщений.  
  
 Этот элемент привязки и его составной кодировщик используются для управления кодировкой в тех сценариях, где не применяется обмен сообщениями по протоколу SOAP, используемый элементом `webHttpBinding`. К таким сценариям относятся: Plain Old XML (POX), REST (Representational State Transfer), RSS (Really Simple Syndication), синдикация Atom и AJAX (Asynchronous JavaScript and XML). Составной кодировщик сообщений не поддерживает SOAP и WS-Addressing.  
  
 В элементе привязки можно задать кодировку записи с помощью атрибута `writeEncoding`. Предоставленное значение <xref:System.Text.Encoding> задает поведение при записи для форматов JSON и XML в текстовом виде. Для чтения поддерживается любая допустимая кодировка сообщений и кодировка текста.  
  
 Атрибуты `maxReadPoolSize` и `maxWritePoolSize` также могут использоваться для установки максимального количества выделяемых обработчиков чтения и записи соответственно. По умолчанию выделяется 64 обработчика чтения и 16 обработчиков записи.  
  
 Ограничения по сложности по умолчанию также устанавливаются с использованием [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) элемент, чтобы защититься от отказ в обслуживании (DOS), направленных на сложность сообщения используется для перегрузки обработки конечной точки ресурсы.  
  
## <a name="example"></a>Пример  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [Кодирование сообщений](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [Выбор кодировщика сообщений](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
