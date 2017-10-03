---
title: '&lt;textMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
caps.latest.revision: 14
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c69b7647fa03cf8a6f83a7e3869da4c7a09161ba
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="lttextmessageencodinggt"></a>&lt;textMessageEncoding&gt;
Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<textMessageEncoding >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|maxReadPoolSize|Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения. Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора. Значение по умолчанию — 64.|  
|maxWritePoolSize|Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи. Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора. Значение по умолчанию — 16.|  
|messageVersion|Задает версию SOAP сообщений, отправленных с помощью привязки. Допустимы следующие значения:<br /><br /> -Soap11Addressing10<br />-Soap12Addressing10<br /><br /> Значение по умолчанию - Soap12Addressing10. Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.|  
|writeEncoding|Задает кодировку, используемую при отправке сообщений через привязку. Допустимы следующие значения:<br /><br /> -UnicodeFffeTextEncoding: Юникод BigEndian<br />-Utf16TextEncoding: Кодировка Юникод<br />-Utf8TextEncoding: 8-разрядная кодировка<br /><br /> Значение по умолчанию - Utf8TextEncoding. Это атрибут типа <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Кодирование — это процесс преобразования сообщения в последовательность байтов. Декодирование представляет собой обратный процесс. В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.  
  
 Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.  Кодировщик текста создает текстовые сообщения в сети. Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-*. Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде. Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.  
  
## <a name="example"></a>Пример  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>   
 [Выбор кодировщика сообщений](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Кодирование сообщений](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

