---
title: "Настройка привязок, предоставляемых системой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], system-provided bindings
- WCF [WCF], system-provided bindings
- bindings [WCF], system-provided
ms.assetid: 443f8d65-f1f2-4311-83b3-4d8fdf7ccf16
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 91994fc31e4b0f30d575cd43ad44e66dcdb0a7f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-system-provided-bindings"></a>Настройка привязок, предоставляемых системой
Привязки указывают, какой механизм связи использовать при взаимодействии с конечной точкой, а также способ подключения к конечной точке. Привязки состоят из элементов, определяющих способ деления каналов [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] на уровни для предоставления требуемых функций связи. Привязка содержит три типа элементов.  
  
-   Элементы привязки канала протокола, определяющие безопасность, надежность, параметры перемещения контекста или пользовательские протоколы, которые используются с сообщениями, отправляемыми в конечную точку.  
  
-   Элементы привязки канала транспорта, определяющие основной транспортный протокол, используемый при отправке сообщений в конечную точку, например TCP или HTTP.  
  
-   Элементы привязки кодирования сообщений, определяющие сетевое кодирование, которое необходимо использовать для сообщений, отправляемых в конечную точку, например кодирование text/XML, двоичное кодирование или подсистема оптимизации передачи сообщений (MTOM).  
  
 В этом разделе представлены все привязки [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], предоставляемые системой. Если ни одна из привязок не отвечает точным требованиям приложения, то можно создать привязку с помощью класса <xref:System.ServiceModel.Channels.CustomBinding>. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]создании пользовательских привязок см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
> [!IMPORTANT]
>  Выберите привязку, в которой включены функции безопасности. По умолчанию функции безопасности всех привязок, за исключением привязки <xref:System.ServiceModel.BasicHttpBinding>, включены. Если безопасная привязка не выбрана или если безопасность выключена, убедитесь, что обмен данными в сети защищен каким-либо иным образом, например выполняется в безопасном центре обработки данных или в изолированной сети.  
  
> [!IMPORTANT]
>  Не используйте дуплексные контракты с привязками, которые не поддерживают безопасность или в которых выключены функции безопасности, если обмен данными в сети не защищен каким-либо иным образом.  
  
## <a name="system-provided-bindings"></a>Привязки, предоставляемые системой  
 Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет следующие привязки.  
  
|Привязка|Элемент конфигурации|Описание|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Привязка, которая подходит для взаимодействия с веб-службами, совместимыми с WS-Basic Profile, например службами, основанными на веб-службах ASP.NET Web (ASMX). Эта привязка использует HTTP как транспорт и формат text/XML как кодирование сообщений по умолчанию.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая подходит для недуплексных контрактов службы.|  
|<xref:System.ServiceModel.WS2007HttpBinding>|[\<ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Безопасная привязка с возможностью взаимодействия, обеспечивающая поддержку правильных версий элементов привязки <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> и <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A>.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая подходит для дуплексных контрактов службы или взаимодействия через посредников SOAP.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая поддерживает протокол WS-Federation и позволяет организациям в федерации выполнять эффективную проверку подлинности и авторизацию пользователей.|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|[\<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая является производной от <xref:System.ServiceModel.WS2007HttpBinding> и поддерживает федеративную безопасность.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Безопасная и оптимизированная привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на разных компьютерах.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Безопасная, надежная и оптимизированная привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на одном компьютере.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Поставленная в очередь привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] на разных компьютерах.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Привязка, которая обеспечивает безопасный обмен данными между несколькими компьютерами.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Привязка, используемая при настройке конечных точек для веб-служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], предоставляемых через HTTP-запросы, а не через сообщения SOAP.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Привязка, которая подходит для обмена данными между приложением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и существующими приложениями очереди сообщений (также называемой MSMQ) на разных компьютерах.|  
  
## <a name="binding-features"></a>Функции привязок  
 В таблице ниже перечислены некоторые ключевые функции каждой указанной привязки, предоставленной системой. Привязки перечислены в первом столбце, а информация, касающаяся функций, представлена в таблице. В следующей таблице приводится ключ к используемым аббревиатурам привязок. Чтобы выбрать привязку, определите, какой столбец удовлетворяет всем требуемым функциям, указанным в строке.  
  
|Привязка|Взаимодействие|Режим безопасности (по умолчанию)|Сеанс<br /><br /> (Значение по умолчанию)|Транзакции|Дуплекс|  
|-------------|----------------------|----------------------------------|-----------------------------|------------------|------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Нет), Транспорт, Сообщение, Смешанный|Нет, (нет)|(Нет)|Н/Д|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Нет, режим безопасности транспорта, (режим безопасности сообщения), смешанный режим|(Нет), сеанс транспорта, надежный сеанс|(Нет), да|Н/Д|  
|<xref:System.ServiceModel.WS2007HttpBinding>|WS-Security, WS-Trust, WS-SecureConversation, WS-SecurityPolicy|Нет, режим безопасности транспорта, (режим безопасности сообщения), смешанный режим|(Нет), сеанс транспорта, надежный сеанс|(Нет), да|Н/Д|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|Нет, (режим безопасности сообщения)|(Надежный сеанс)|(Нет), да|Да|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|Нет, (режим безопасности сообщения), смешанный режим|(Нет), надежный сеанс|(Нет), да|Нет|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|WS-Federation|Нет, (режим безопасности сообщения), смешанный режим|(Нет), надежный сеанс|(Нет), да|Нет|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|Нет, (режим безопасности транспорта), режим безопасности сообщения<br /><br /> Mixed|Надежный сеанс, (сеанс транспорта)|(Нет), да|Да|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|Нет,<br /><br /> (Транспорт)|Нет, (Транспорт)|(Нет), да|Да|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Нет, режим безопасности сообщения, (режим безопасности транспорта), оба режима|(Нет)|(Нет), да|Нет|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Одноранговый узел|Нет, режим безопасности сообщения, (режим безопасности транспорта), смешанный режим|(Нет)|(Нет)|Да|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|Нет, (Транспорт)|(Нет)|(Нет), да|Н/Д|  
  
 В таблице ниже приводятся пояснения функций, указанных в предыдущей таблице.  
  
|Функция|Описание|  
|-------------|-----------------|  
|Тип взаимодействия|Указывает протокол или технологию, взаимодействие с которыми обеспечивает привязка.|  
|Безопасность|Указывает способ защиты канала.<br /><br /> — None: Сообщение SOAP не защищено, и клиент не прошел проверку подлинности.<br />-Транспорта: Требования безопасности выполняются на транспортном уровне.<br />-Сообщения: Требования безопасности выполняются на уровне сообщений.<br />-Смешанный режим: Этот режим безопасности называется `TransportWithMessageCredentials`. В этом режиме учетные данные обрабатываются на уровне сообщений, а требования целостности и конфиденциальности выполняются на транспортном уровне.<br />-Оба: Используются оба транспорта и уровне безопасность на уровне сообщений. Эта возможность уникальна для привязки <xref:System.ServiceModel.NetMsmqBinding>.|  
|Сеанс|Указывает, поддерживает ли привязка контракты сеансов.|  
|Транзакции|Указывает, включены ли транзакции.|  
|Дуплекс|Указывает, поддерживаются ли дуплексные контракты. Обратите внимание, что для этой функции необходима поддержка сеансов в привязке.|  
|Потоковые операторы|Указывает, поддерживается ли потоковая передача сообщений.|  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о создании конечных точек](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Использование привязок для настройки служб и клиентов](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Базовое программирование для WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)
