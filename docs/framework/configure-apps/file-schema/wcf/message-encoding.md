---
title: Message Encoding
ms.date: 03/30/2017
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
ms.openlocfilehash: d797b810af5df5fc1acf31e0ab6338689da9f55c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734017"
---
# <a name="message-encoding"></a>Message Encoding
Кодирование - это процесс преобразования набора символов Юникода в последовательность байтов. Декодирование представляет собой обратный процесс. Windows Communication Foundation (WCF) включает в себя три типа кодирования для сообщений SOAP: Текст, двоичное кодирование и механизм оптимизации передачи сообщений (MTOM).  
  
 В разделе конфигурации `binaryMessageEncoding` указывается кодировка символов и управление версиями сообщений, используемые для двоичных сообщений XML. Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети. Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-*.  
  
 В разделе конфигурации `mtomMessageEncoding` указывается кодировка символов и управление версиями сообщений, используемые для сообщения с помощью кодирования MTOM (Message Transmission Optimization Mechanism). MTOM - это эффективная технология для передачи двоичных данных в сообщениях Windows Communication Foundation. Кодировщик MTOM предпринимает попытку соблюсти баланс между эффективностью и взаимодействием. Кодирование MTOM передает большую часть XML-данных в текстовой форме, но оптимизирует большие блоки двоичных данных путем передачи их в исходном виде, без преобразования в текст.  
  
 В разделе конфигурации `textMessageEncoding` указывается кодировщик текста, используемый для создания текстовых сообщений в сети. Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-*. Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде. Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Выбор кодировщика сообщений](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
