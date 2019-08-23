---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 9b6b74200c807e6523ed3f7250945040bd12658d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919798"
---
# <a name="binarymessageencoding"></a>\<Бинаримессажеенкодинг >
Определяет кодировщик двоичных сообщений, кодирующий сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Бинаримессажеенкодинг >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|maxReadPoolSize|Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения. Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора. Значение по умолчанию — 64.|  
|maxSessionSize|Положительное целое число, задающее размер буфера, используемого для кодирования (в байтах). Буфер большего размера повышает скорость кодирования за счет размера рабочего набора. Значение по умолчанию — 2048.|  
|maxWritePoolSize|Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи. Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора. Значение по умолчанию — 16.|  
|messageVersion|Определяет используемые или ожидаемые версии сообщения SOAP и WS-Addressing.|  
  
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
  
 Элемент `binaryMessageEncoding` указывает двоичный формат .NET для XML и содержит параметры, задающие кодировку символов и версию SOAP и WS-Addressing для использования. Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети. Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-*.  
  
## <a name="example"></a>Пример  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [Кодирование сообщений](message-encoding.md)
- [Выбор кодировщика сообщений](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
