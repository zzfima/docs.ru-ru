---
title: Настраиваемый диспетчер каналов
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: ea1bdd470855d1b2f6572a15ce45f9b90d74fdca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145129"
---
# <a name="custom-channel-dispatcher"></a>Настраиваемый диспетчер каналов
Этот образец демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла. Диспетчер каналов взаимодействует с <xref:System.ServiceModel.Channels.IChannelListener> для принятия каналов и получения сообщений из стека каналов. В рамках этого образца также представлен базовый образец, показывающий, как построить стек каналов в среде веб-узла с помощью <xref:System.ServiceModel.Activation.VirtualPathExtension>.  
  
## <a name="custom-servicehostbase"></a>Пользовательский ServiceHostBase  
 Этот пример реализует базовый <xref:System.ServiceModel.ServiceHostBase> <xref:System.ServiceModel.ServiceHost> тип вместо того, чтобы продемонстрировать, как заменить реализацию стека Windows Communication Foundation (WCF) на пользовательский слой обработки сообщений в верхней части стека каналов. Для построения прослушивателей и диспетчера каналов переопределяется виртуальный метод <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>.  
  
 Чтобы реализовать службу, размещенную на веб-сервере, возвратите расширение службы <xref:System.ServiceModel.Activation.VirtualPathExtension> из коллекции <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> и добавьте его в коллекцию <xref:System.ServiceModel.Channels.BindingParameterCollection>, чтобы транспортному слою было известно, как настроить прослушиватель канала на основе параметров среды размещения, то есть параметров служб IIS/службы активации Windows (WAS).  
  
## <a name="custom-channel-dispatcher"></a>Настраиваемый диспетчер каналов  
 Пользовательский диспетчер каналов расширяет тип <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>. Этот тип реализует логику программирования уровня канала. В этом образце для шаблона обмена сообщениями «запрос-ответ» поддерживается только <xref:System.ServiceModel.Channels.IReplyChannel>, при этом пользовательский диспетчер каналов можно легко расширить, добавив другие типы каналов.  
  
 Сначала диспетчер открывает прослушиватель каналов, а затем принимает одноэлементный канал ответа. По этому каналу он запускает бесконечный цикл отправки сообщений (запросов). По каждому запросу он создает ответное сообщение и отправляет его назад клиенту.  
  
## <a name="creating-a-response-message"></a>Создание ответного сообщения  
 Обработка сообщений реализуется в типе `MyServiceManager`. В методе `HandleRequest` сначала проверяется заголовок `Action` сообщения, чтобы выяснить, поддерживается ли запрос. Предопределенное действиеhttp://tempuri.org/HelloWorld/HelloSOAP " определяется для обеспечения фильтрации сообщений. Это похоже на концепцию контракта на обслуживание <xref:System.ServiceModel.ServiceHost>в реализации WCF .  
  
 Для выбора правильного действия протокола SOAP образец получает запрошенные данные сообщения и формирует соответствующий ответ на запрос, аналогично случаю <xref:System.ServiceModel.ServiceHost>.  
  
 В этом случае команда HTTP-GET была специально обработана путем возврата пользовательского сообщения HTTP с тем, чтобы можно было открыть службу в браузере, чтобы удостовериться, что она правильно скомпилирована. Если действие протокола SOAP не совпадает, отправьте сообщение об ошибке, чтобы указать, что запрос не поддерживается.  
  
 Клиент этого образца является нормальным клиентом WCF, который ничего не предполагает от службы. Таким образом, услуга специально разработана, чтобы соответствовать<xref:System.ServiceModel.ServiceHost> тому, что вы получаете от нормальной реализации WCF. В результате этого в клиенте требуется наличие только контракта службы.  
  
## <a name="using-the-sample"></a>Использование образца  
 При прямом запуске клиентского приложения формируется следующий результат.  
  
```output  
Client is talking to a request/reply WCF service.
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 Службу также можно открыть в браузере с тем, чтобы сообщение HTTP-GET было обработано на сервере. При этом возвращается хорошо отформатированный текст в формате HTML.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
