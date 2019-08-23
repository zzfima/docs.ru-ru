---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e2fec2c2e5979b08ed0d832f636b3d0847b9a5dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915662"
---
# <a name="textmessageencoding"></a>\<Текстмессажеенкодинг >
Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Текстмессажеенкодинг >  
  
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
|messageVersion|Задает версию SOAP сообщений, отправленных с помощью привязки. Допустимы следующие значения:<br /><br /> - Soap11Addressing10<br />- Soap12Addressing10<br />-Soap11<br />-Soap12<br /><br />Значение по умолчанию - Soap12Addressing10. Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.|  
|writeEncoding|Задает кодировку, используемую при отправке сообщений через привязку. Допустимы следующие значения:<br /><br /> -Уникодефффетекстенкодинг: Кодировка байтов Юникода<br />- Utf16TextEncoding: Кодировка Юникод<br />- Utf8TextEncoding: 8-разрядная кодировка<br /><br /> Значение по умолчанию - Utf8TextEncoding. Это атрибут типа <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Кодирование — это процесс преобразования сообщения в последовательность байтов. Декодирование представляет собой обратный процесс. Windows Communication Foundation (WCF) включает три типа кодировки для сообщений SOAP: Text, binary и механизм оптимизации передачи сообщений (MTOM).  
  
 Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.  Кодировщик текста создает текстовые сообщения в сети. Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-*. Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде. Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.  
  
## <a name="example"></a>Пример  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [Выбор кодировщика сообщений](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [Кодирование сообщений](message-encoding.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
