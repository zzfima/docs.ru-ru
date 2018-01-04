---
title: "Расширяемость каналов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 541770db6b9cc624fd08ab4db275bc63fa5deca9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="channels-extensibility"></a>Расширяемость каналов
В этом разделе содержатся образцы, демонстрирующие пользовательские каналы.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Локальный канал](../../../../docs/framework/wcf/samples/local-channel.md)  
 Демонстрирует локальный канал транспорта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который используется для связи внутри одного домена приложения.  
  
 [Надежный защищенный профиль](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 Показано использование [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместе с надежным защищенным профилем (RSP).  
  
 [Настраиваемый диспетчер каналов](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 Демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла.  
  
 [Фрагментирование канала](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 Показывает способы ограничения объема памяти, используемого для буферизации больших сообщений, отправляемых с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Канал подтверждений HTTP](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 Демонстрирует многоуровневый канал, изменяющий односторонний шаблон обмена сообщениями.  
  
 [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 Демонстрирует, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP.  
  
 [Пользовательский перехватчик сообщений](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 Показано, как реализовать пользовательский элемент привязки, который создает фабрики и прослушиватели каналов для перехвата всех входящих и исходящих сообщений в определенной точке стека времени выполнения.
