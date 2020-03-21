---
title: Протокол обмена контекстом
ms.date: 03/30/2017
ms.assetid: 3dfd38e0-ae52-491c-94f4-7a862b9843d4
ms.openlocfilehash: 00adb68d96f77ce0953811d13b5377ec4ed1e0ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185267"
---
# <a name="context-exchange-protocol"></a>Протокол обмена контекстом
В этом разделе описывается протокол обмена контекстами, представленный в версии 3.NET Framework Foundation .NET. Этот протокол позволяет клиентскому каналу принимать контекст, предоставленный службой, и применять его ко всем последующим запросам, поступающим в эту службу через тот же экземпляр клиентского канала. Для распространения контекста между сервером и клиентом реализация протокола обмена контекстом может использовать один из двух механизмов: файлы cookie HTTP или заголовок SOAP.  
  
 Протокол обмена контекстом реализуется на уровне пользовательских каналов. Канал передает контекст на уровень приложения и обратно с помощью свойства <xref:System.ServiceModel.Channels.ContextMessageProperty>. Для передачи данных между конечными точками значение контекста либо сериализуется в качестве заголовка SOAP на уровне канала, либо преобразуется в свойства сообщения, представляющие HTTP-запрос и ответ. В последнем случае предполагается, что один из используемых уровней канала преобразует свойства сообщений HTTP-запроса и ответа в файлы cookie HTTP и обратно соответственно. Выбор механизма обмена контекстом осуществляется с помощью свойства <xref:System.ServiceModel.Channels.ContextExchangeMechanism> в элементе привязки <xref:System.ServiceModel.Channels.ContextBindingElement>. Допустимые значения: `HttpCookie` или `SoapHeader`.  
  
 На стороне клиента экземпляр канала может работать в двух режимах на основе параметров в свойстве канала <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A>.  
  
## <a name="mode-1-channel-context-management"></a>Режим 1: управление контекстом канала  
 Этот режим используется по умолчанию, если параметру <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> задано значение `true`. В этом режиме канал контекста управляет контекстом и кэширует его в течение времени его существования. Контекст может быть извлечен из канала с помощью свойства канала `IContextManager` вызовом метода `GetContext`. Можно также заранее инициализировать канал с конкретным контекстом до его открытия вызовом метода `SetContext` для свойства канала. Если канал инициализирован с контекстом, его сброс невозможен.  
  
 В этом режиме перечисленное ниже остается неизменным.  
  
- Любая попытка сброса контекста с помощью `SetContext` после того, как канал был открыт, приводит к возникновению исключения <xref:System.InvalidOperationException>.  
  
- Любая попытка отправить контекст с использованием свойства <xref:System.ServiceModel.Channels.ContextMessageProperty> в исходящем сообщении вызывает исключение <xref:System.InvalidOperationException>.  
  
- Если от сервера получено сообщение с конкретным контекстом, а канал уже инициализирован с конкретным контекстом, создается исключение <xref:System.ServiceModel.ProtocolException>.  
  
    > [!NOTE]
    > Рекомендуется получать исходный контекст с сервера, только если канал был открыт без явного задания контекста.  
  
- Свойство <xref:System.ServiceModel.Channels.ContextMessageProperty> для входящего сообщения всегда null.  
  
## <a name="mode-2-application-context-management"></a>Режим 2: управление контекстом приложения  
 Этот режим используется, если свойству <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> присвоено значение `false`. В этом режиме канал контекста не управляет контекстом. Ответственность за извлечение, обработку и применение контекста с использованием свойства <xref:System.ServiceModel.Channels.ContextMessageProperty> возлагается на приложение. Любая попытка вызова метода `GetContext` или `SetContext` приводит к возникновению исключения <xref:System.InvalidOperationException>.  
  
 Независимо от выбранного режима работы фабрика клиентских каналов поддерживает шаблоны обмена сообщениями <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel> и <xref:System.ServiceModel.Channels.IDuplexSessionChannel>  
  
 На стороне службы ответственность за преобразование контекста, предоставленного клиентом для входящих сообщений, в свойство сообщения <xref:System.ServiceModel.Channels.ContextMessageProperty> возлагается на экземпляр канала. Впоследствии доступ к свойству сообщения может осуществляться на уровне приложения или с использованием других каналов далее в стеке вызова. Каналы служб также позволяют указывать новое значение контекста на уровне приложения, которое затем будет распространяться обратно клиенту, путем присоединения свойства <xref:System.ServiceModel.Channels.ContextMessageProperty> к ответному сообщению. Это свойство преобразуется в заголовок SOAP или файл cookie HTTP, который содержит контекст, зависящий от конфигурации привязки. Прослушиватель канала служб поддерживает шаблоны обмена сообщениями <xref:System.ServiceModel.Channels.IReplyChannel>, <xref:System.ServiceModel.Channels.IReplySessionChannel> и <xref:System.ServiceModel.Channels.IReplySessionChannel>.  
  
 Протокол обмена контекстом вводит новый заголовок SOAP `wsc:Context` для представления сведений контекста, если для распространения контекста не используются файлы cookie HTTP. Схема заголовка контекста допускает включение любого числа дочерних элементов, каждый из которых имеет строковый ключ и строковое содержимое. Ниже приведен пример заголовка контекста.  
  
 `<Context xmlns="http://schemas.microsoft.com/ws/2006/05/context">`  
  
 `<property name="myContext">context-2</property>`  
  
 `</Context>`  
  
 При работе в режиме `HttpCookie` файлы cookie задаются с использованием заголовка `SetCookie`. Имя файла cookie - `WscContext`. Значением файла cookie является кодировка Base64 заголовка `wsc:Context`. Это значение заключено в кавычки.  
  
 Значение контекста должно быть защищено от изменения во время передачи по тем же причинам, по которым защищаются заголовки WS-Addressing: этот заголовок используется, чтобы определить, куда передавать запрос в службе. Поэтому требуется, чтобы заголовок `wsc:Context` имел цифровую подпись или был зашифрован на уровне SOAP или на транспортном уровне, если привязка обеспечивает возможность защиты сообщений. Если для распространения контекста используются файлы cookie HTTP, они должны быть защищены с помощью системы безопасности транспорта.  
  
 Конечные точки службы, которым требуется поддержка протокола обмена контекстом, могут явно объявить об этом в опубликованной политике. Были введены два новых утверждения политики, предъявляющие требование к клиенту, чтобы он поддерживал протокол обмена контекстом на уровне SOAP или была включена поддержка файлов cookie HTTP. Создание этих утверждений в политике службы управляется значением свойства <xref:System.ServiceModel.Channels.ContextBindingElement.ContextExchangeMechanism%2A>, как показано ниже.  
  
- Для <xref:System.ServiceModel.Channels.ContextExchangeMechanism.ContextSoapHeader> создается следующее утверждение  
  
    ```xml  
    <IncludeContext
    xmlns="http://schemas.microsoft.com/ws/2006/05/context"  
    protectionLevel="Sign" />  
    ```  
  
- Для <xref:System.ServiceModel.Channels.ContextExchangeMechanism.HttpCookie> создается следующее утверждение  
  
    ```xml  
    <HttpUseCookie xmlns="http://schemas.xmlsoap.org/soap/http"/>  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Руководство по взаимодействию по протоколам веб-служб](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)
