---
title: "Привязки, предоставляемые системой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
caps.latest.revision: "60"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea5cd7f8510836b17a20b523dc2455611cdb2382
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="system-provided-bindings"></a>Привязки, предоставляемые системой
Привязки указывают, какой механизм связи использовать при взаимодействии с конечной точкой, а также способ подключения к конечной точке. Привязка содержит следующие элементы.  
  
-   Элемент стека протоколов определяет параметры безопасности, надежности и перемещения контекста, используемые для отправляемых конечной точке сообщений.  
  
-   Элемент транспорта определяет основной транспортный протокол, используемый при отправке сообщений конечной точке, например TCP или HTTP.  
  
-   Элемент кодирования определяет кодирование на линии связи, используемое для отправляемых конечной точке сообщений, например кодирование text/XML, двоичное кодирование или кодирование подсистемы оптимизации передачи сообщений (MTOM).  
  
 В этом разделе представлены все привязки [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], предоставляемые системой. Если ни одна из привязок не отвечает в точности требованиям приложения, можно создать пользовательскую привязку. [!INCLUDE[crabout](../../../includes/crabout-md.md)]создании пользовательских привязок см. в разделе [пользовательские привязки](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Безопасная привязка с возможностью взаимодействия, которая поддерживает протокол WS-Federation, позволяет организациям в федерации эффективно проверять подлинность пользователей и авторизовать их.  
  
> [!IMPORTANT]
>  Следует всегда выбирать привязку, предусматривающую функции безопасности. По умолчанию, все привязки, за исключением [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемент разрешено обеспечение безопасности. При выборе привязки без функций безопасности или при отключении функций безопасности обязательно защищайте данные каким-либо иным способом, например путем хранения в защищенном центре обработки данных или в изолированной сети.  
  
> [!IMPORTANT]
>  Не используйте дуплексные контракты с привязками, которые не поддерживают безопасность или в которых отключены функции безопасности, если данные не защищены каким-либо иным образом.  
  
## <a name="system-provided-bindings"></a>Привязки, предоставляемые системой  
 В состав [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] входят следующие привязки.  
  
|Привязка|Элемент конфигурации|Описание|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Привязка, которая подходит для взаимодействия с веб-службами, совместимыми с WS-Basic Profile, например службами, основанными на веб-службах ASP.NET Web (ASMX). Эта привязка использует HTTP как транспорт и формат text/XML как кодирование сообщений по умолчанию.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая подходит для недуплексных контрактов службы.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая подходит для дуплексных контрактов службы или взаимодействия через посредников SOAP.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Безопасная привязка с возможностью взаимодействия, которая поддерживает протокол WS-Federation, позволяющий организациям в федерации эффективно проверять подлинность пользователей и авторизовать их.|  
|<xref:System.ServiceModel.NetHttpBinding>|\<Привязка netHttpBinding >|Привязка, предназначенная для работы со службами HTTP или WebSocket и использующая по умолчанию двоичное кодирование.|  
|<xref:System.ServiceModel.NetHttpsBinding>|\<Привязка netHttpsBinding >|Безопасная привязка, предназначенная для работы со службами HTTP или WebSocket и использующая по умолчанию двоичное кодирование.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Безопасная и оптимизированная привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на разных компьютерах.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Безопасная, надежная и оптимизированная привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на одном компьютере.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Поставленная в очередь привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на разных компьютерах.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Привязка, которая обеспечивает безопасный обмен данными между несколькими компьютерами.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding >](../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Привязка, которая подходит для обмена данными между приложением [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и существующими приложениями очереди сообщений (MSMQ) на разных компьютерах.|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpcontextbinding.md)|Привязка, которая подходит для обмена данными с веб-службами, совместимыми с WS-Basic Profile, и позволяет использовать для обмена контекстом файлы cookie HTTP.|  
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpcontextbinding.md)|Безопасная и оптимизированная привязка, которая подходит для обмена данными между приложениями [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на разных компьютерах и позволяет использовать для обмена контекстом заголовки SOAP.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Привязка, используемая при настройке конечных точек для веб-служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], предоставляемых через HTTP-запросы, а не через сообщения SOAP.|  
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpcontextbinding.md)|Безопасный и |<xref:System.ServiceModel.UdpBinding>|\<udpBinding >|Привязка, используемая при отправке группы простых сообщений большому количеству клиентов одновременно.|  
  
 В следующей таблице приведены функции каждой предоставляемой системой привязки. В столбцах таблицы приведены привязки; функции приведены в строках и подробно описаны во второй таблице. В следующей таблице приводится ключ к используемым аббревиатурам привязок. Чтобы выбрать привязку, определите, какой столбец удовлетворяет всем требуемым функциям, указанным в строке.  
  
|Привязка|Взаимодействие|Режим безопасности (по умолчанию)|Сеанс<br /><br /> (Значение по умолчанию)|Транзакции|Дуплекс|Кодирование (по умолчанию)|Потоковые операторы<br /><br /> (Значение по умолчанию)|  
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Нет), Транспорт, Сообщение, Смешанный|(Нет)|(Нет)|Н/Д|Текстовое, (MTOM)|Да<br /><br /> (с буферизацией)|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Транспорта, (сообщения), смешанный|(Нет), Надежный сеанс, Безопасный сеанс|(Нет), да|Н/Д|(Текстовое), MTOM|Нет|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Сообщения), нет|(Надежный сеанс), Безопасный сеанс|(Нет), да|Да|(Текстовое), MTOM|Нет|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Сообщения), смешанный, нет|(Нет), Надежный сеанс, Безопасный сеанс|(Нет), да|Нет|(Текстовое), MTOM|Нет|  
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(Нет), Транспорт, Сообщение, TransportWithMessageCredential, TransportCredentialOnly|См. примечание ниже|Нет|См. примечание ниже|(Двоичная), Текст, MTOM|Да (с буферизацией)|  
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(Транспорт), TransportWithMessageCredential|См. примечание ниже|Нет|См. примечание ниже|(Двоичная), Текст, MTOM|Да (с буферизацией)|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Транспорта), сообщения, нет, смешанный|(Транспорт), Надежный сеанс, Безопасный сеанс|(Нет), да|Да|Binary|Да<br /><br /> (с буферизацией)|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Транспорта), нет|Нет, (Транспорт)|(Нет), да|Да|Binary|Да<br /><br /> (с буферизацией)|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Сообщения, (транспорта), нет|(Нет), Транспорт|(Нет), да|Нет|Binary|Нет|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Одноранговый узел|(Транспорт)|(Нет)|(Нет)|Да||Нет|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|(Транспорт)|(Нет)|(Нет), да|Н/Д|Н/Д|Нет|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(Нет), Транспорт, Сообщение, Смешанный|(Нет)|(Нет)|Н/Д|Текстовое, (MTOM)|Да<br /><br /> (с буферизацией)|  
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Транспорта), сообщения, нет, смешанный|(Транспорт), Надежный сеанс, Безопасный сеанс|(Нет), да|Да|Binary|Да<br /><br /> (с буферизацией)|  
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Транспорта, (сообщения), смешанный|(Нет), Надежный сеанс, Безопасный сеанс|(Нет), да|Н/Д|Текстовое, (MTOM)|Нет|  
|<xref:System.ServiceModel.UdpBinding>|.NET **Примечание:** добиться взаимодействия можно путем реализации стандартной SOAP через UDP реализуемой этой привязкой.|(Нет)|(Нет)|(Нет)|Н/Д|(Текст)|Нет|  
  
> [!IMPORTANT]
>  <xref:System.ServiceModel.NetHttpBinding> - это привязка, предназначенная для использования служб HTTP или WebSocket и использующая по умолчанию двоичное кодирование. <xref:System.ServiceModel.NetHttpBinding> определяет, будет ли она использоваться с дуплексным контрактом и контрактом типа «запрос-ответ» и изменит ли свое поведение для соответствия контракту. HTTP будет использоваться для контрактов типа «запрос-ответ», и WebSockets - для дуплексных контрактов. Это поведение можно переопределить с помощью <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A>--> `System.ServiceModel.NetHttpBinding.WebSocketTransportUsage` параметра привязки: разрешена - это значение по умолчанию и работает, как описано выше. Не разрешено - запрещает использование WebSockets используется. Попытка использования дуплексного контракта с этим параметром приведет к возникновению исключения. Требуется - это обеспечивает использование службы WebSockets даже для контрактов типа запрос ответ. Привязка NetHttpBinding поддерживает надежные сеансы в режиме HTTP и в режиме WebSocket. В режиме WebSocket сеансы предоставляются транспортом.  
  
 В следующей таблице поясняются функции, упомянутые в предыдущей таблице.  
  
|Функция|Описание|  
|-------------|-----------------|  
|Тип взаимодействия|Указывает протокол или технологию, взаимодействие с которыми обеспечивает привязка.|  
|Безопасность|Указывает способ защиты канала.<br /><br /> — None: Сообщение SOAP не защищено, и клиент не прошел проверку подлинности.<br />-Транспорта: Требования безопасности выполняются на транспортном уровне.<br />-Сообщения: Требования безопасности выполняются на уровне сообщений.<br />-Смешанный: Утверждения передаются в сообщении; требования целостности и конфиденциальности обеспечиваются на транспортном уровне.|  
|Сеанс|Указывает, поддерживает ли привязка контракты сеансов.|  
|Транзакции|Указывает, включены ли транзакции.|  
|Дуплекс|Указывает, поддерживаются ли дуплексные контракты. Обратите внимание, что для этой функции необходима поддержка сеансов в привязке.|  
|кодировка|Указывает формат сообщения при передаче по линиям связи. Допустимые значения:<br /><br /> -Текст: например, UTF-8.<br />-Двоичный<br />-Механизм оптимизации передачи сообщений (MTOM): Метод эффективного кодирования двоичных XML-элементов в контексте конверта SOAP.|  
|Потоковые операторы|Указывает, поддерживается ли потоковая передача входящих и исходящих сообщений. Для задания этого значения используется свойство `TransferMode` привязки. Допустимые значения:<br /><br /> -   <xref:System.ServiceModel.TransferMode.Buffered>: Сообщения запроса и ответа буферизуются.<br />-   <xref:System.ServiceModel.TransferMode.Streamed>: Сообщения запроса и ответа передаются потоком.<br />-   <xref:System.ServiceModel.TransferMode.StreamedRequest>: Сообщение запроса передается потоком, а сообщение ответа буферизуется.<br />-   <xref:System.ServiceModel.TransferMode.StreamedResponse>: Сообщение запроса буферизируется, а сообщение ответа передается потоком.|  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о создании конечных точек](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Базовое программирование для WCF](../../../docs/framework/wcf/basic-wcf-programming.md)
