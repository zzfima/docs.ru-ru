---
title: Настраиваемый диспетчер каналов
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: 2f7bb67f45c3aa9eb0cb58fa2f30744d5500fab0
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="custom-channel-dispatcher"></a>Настраиваемый диспетчер каналов
Этот образец демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла. Диспетчер каналов взаимодействует с <xref:System.ServiceModel.Channels.IChannelListener> для принятия каналов и получения сообщений из стека каналов. В рамках этого образца также представлен базовый образец, показывающий, как построить стек каналов в среде веб-узла с помощью <xref:System.ServiceModel.Activation.VirtualPathExtension>.  
  
## <a name="custom-servicehostbase"></a>Пользовательский ServiceHostBase  
 Этот образец реализует базовый тип <xref:System.ServiceModel.ServiceHostBase> вместо <xref:System.ServiceModel.ServiceHost> для демонстрации замены реализации стека Windows Communication Foundation (WCF) с пользовательской уровнем обработки сообщений поверх стека каналов. Для построения прослушивателей и диспетчера каналов переопределяется виртуальный метод <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>.  
  
 Чтобы реализовать службу, размещенную на веб-сервере, возвратите расширение службы <xref:System.ServiceModel.Activation.VirtualPathExtension> из коллекции <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> и добавьте его в коллекцию <xref:System.ServiceModel.Channels.BindingParameterCollection>, чтобы транспортному слою было известно, как настроить прослушиватель канала на основе параметров среды размещения, то есть параметров служб IIS/службы активации Windows (WAS).  
  
## <a name="custom-channel-dispatcher"></a>Настраиваемый диспетчер каналов  
 Пользовательский диспетчер каналов расширяет тип <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>. Этот тип реализует логику программирования уровня канала. В этом образце для шаблона обмена сообщениями «запрос-ответ» поддерживается только <xref:System.ServiceModel.Channels.IReplyChannel>, при этом пользовательский диспетчер каналов можно легко расширить, добавив другие типы каналов.  
  
 Сначала диспетчер открывает прослушиватель каналов, а затем принимает одноэлементный канал ответа. По этому каналу он запускает бесконечный цикл отправки сообщений (запросов). По каждому запросу он создает ответное сообщение и отправляет его назад клиенту.  
  
## <a name="creating-a-response-message"></a>Создание ответного сообщения  
 Обработка сообщений реализуется в типе `MyServiceManager`. В методе `HandleRequest` сначала проверяется заголовок `Action` сообщения, чтобы выяснить, поддерживается ли запрос. Предварительно заданное действие SOAP «http://tempuri.org/HelloWorld/Hello» определено для выполнения фильтрации сообщений. Это похоже на концепцию контракта службы в реализации WCF <xref:System.ServiceModel.ServiceHost>.  
  
 Для выбора правильного действия протокола SOAP образец получает запрошенные данные сообщения и формирует соответствующий ответ на запрос, аналогично случаю <xref:System.ServiceModel.ServiceHost>.  
  
 В этом случае команда HTTP-GET была специально обработана путем возврата пользовательского сообщения HTTP с тем, чтобы можно было открыть службу в браузере, чтобы удостовериться, что она правильно скомпилирована. Если действие протокола SOAP не совпадает, отправьте сообщение об ошибке, чтобы указать, что запрос не поддерживается.  
  
 Клиент в этом примере является обычной клиента WCF, который отличается от службы. Таким образом, службы создана с учетом соответствия результатам из обычных WCF<xref:System.ServiceModel.ServiceHost> реализации. В результате этого в клиенте требуется наличие только контракта службы.  
  
## <a name="using-the-sample"></a>Использование образца  
 При прямом запуске клиентского приложения формируется следующий результат.  
  
```Output  
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
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
