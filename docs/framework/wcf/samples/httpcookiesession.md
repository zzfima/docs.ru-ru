---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: 815f6917413afebc71f0ec6e1c81eb1de14547a4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876795"
---
# <a name="httpcookiesession"></a>HttpCookieSession
В этом образце показано, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP. Этот канал обеспечивает взаимодействие между службами Windows Communication Foundation (WCF) и клиентами ASMX или между клиентами и службами ASMX WCF.  
  
 Когда клиент вызывает веб-метод ASMX веб-службы, на основе сеансов, механизм ASP.NET выполняет следующие функции:  
  
- создает уникальный идентификатор сеанса;  
  
- создает объект сеанса и связывает его с уникальным идентификатором;  
  
- добавляет уникальный идентификатор в заголовок HTTP-ответа Set-Cookie и отправляет его клиенту;  
  
- определяет клиент в последующих вызовах по идентификатору сеанса и использует его для отправки сообщений.  
  
 Клиент включает этот идентификатор сеанса во все дальнейшие запросы к серверу. Сервер использует идентификатор сеанса клиента, чтобы загружать соответствующий объект сеанса для текущего контекста HTTP.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a>Шаблон обмена сообщениями канала HttpCookieSession  
 В этом примере включаются сеансы для сценариев, подобных применению служб ASMX. В нижней части стека каналов имеется транспорт HTTP, который поддерживает <xref:System.ServiceModel.Channels.IRequestChannel> и <xref:System.ServiceModel.Channels.IReplyChannel>. Именно канал отвечает за то, чтобы предоставлять сеансы каналам стека более высокого уровня. В образце реализуются два канала (<xref:System.ServiceModel.Channels.IRequestSessionChannel> и <xref:System.ServiceModel.Channels.IReplySessionChannel>), поддерживающих сеансы.  
  
## <a name="service-channel"></a>Канал службы  
 В этом образце создается канал службы в классе `HttpCookieReplySessionChannelListener`. Этот класс реализует интерфейс <xref:System.ServiceModel.Channels.IChannelListener> и преобразует канал <xref:System.ServiceModel.Channels.IReplyChannel> из нижнего канала в стеке в канал <xref:System.ServiceModel.Channels.IReplySessionChannel>. Этот процесс можно разбить на следующие части.  
  
- Когда открывается прослушиватель канала, он принимает от своего внутреннего прослушивателя внутренний канал. Поскольку внутренний прослушиватель является прослушивателем датаграмм, а время существования принятого канала вычитается из времени существования прослушивателя, можно закрыть внутренний прослушиватель и работать только с внутренним каналом.  
  
    ```  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- После завершения процесса открытия мы настраиваем цикл сообщений, чтобы получать сообщения от внутреннего канала.  
  
    ```  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       if (this.completeReceiveCallback == null)  
       {  
          this.completeReceiveCallback = new WaitCallback(CompleteReceiveCallback);  
       }  
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- Когда сообщение прибывает, канал службы проверяет идентификатор сеанса и демультиплексирует его в соответствующий канал сеанса. Прослушиватель канала поддерживает словарь, который сопоставляет идентификаторы сеансов с экземплярами каналов сеансов.  
  
    ```  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 `HttpCookieReplySessionChannel` Класс реализует <xref:System.ServiceModel.Channels.IReplySessionChannel>. Более высокие уровня стека каналов вызывают метод <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> для чтения запросов для этого сеанса. У каждого канала сеанса имеется закрытая очередь сообщений, заполняемая каналом службы.  
  
```  
InputQueue<RequestContext> requestQueue;  
```  
  
 Если происходит вызов метода <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>, а в очереди сообщений нет сообщений, то канал ждет в течение заданного времени, а затем отключается. Это позволяет избавиться от каналов сеансов, созданных для клиентов WCF.  
  
 Мы используем `channelMapping` для отслеживания `ReplySessionChannels` и не закрываем соответствующий канал `innerChannel`, пока не будут закрыты все принятые каналы. Таким образом, канал `HttpCookieReplySessionChannel` может существовать после истечения времени существования `HttpCookieReplySessionChannelListener`. Кроме того, нам не нужно беспокоиться о попадании прослушивателя под сборку мусора, поскольку принятые каналы сохраняют ссылку на свой прослушиватель с помощью обратного вызова `OnClosed`.  
  
## <a name="client-channel"></a>Клиентский канал  
 Соответствующий клиентский канал создается в классе `HttpCookieSessionChannelFactory`. Во время создания канал фабрика каналов с помощью `HttpCookieRequestSessionChannel` создает оболочку для внутреннего канала запросов. Класс `HttpCookieRequestSessionChannel` перенаправляет вызовы в соответствующий канал запросов. Когда клиент закрывает прокси, `HttpCookieRequestSessionChannel` отправляет службе сообщение о том, что канал закрывается. Таким образом, стек каналов службы может безопасно закрыть используемый канал сеанса.  
  
## <a name="binding-and-binding-element"></a>Привязка и элемент привязки  
 После создания каналов служба и клиент, следующим шагом является их интеграция в среду выполнения WCF. Каналы предоставляются через привязки и элементы привязки WCF. Привязка состоит из одного или нескольких элементов привязки. WCF предлагает несколько привязок, определенных системой; Например, BasicHttpBinding или WSHttpBinding. Класс `HttpCookieSessionBindingElement` содержит реализацию элемента привязки. Он переопределяет прослушиватель канала и методы создания фабрики канала для создания нужных экземпляров прослушивателя канала и фабрики каналов.  
  
 В этом образце для описания службы используются утверждения политики. Это позволяет образцу публиковать свои требования к каналам для других клиентов, которые могут пользоваться службой. Например, этот элемент привязки публикует утверждения политики, позволяющие потенциальным клиентам узнать, служба поддерживает сеансы. Поскольку в конфигурации элемента привязки этого образца включено свойство `ExchangeTerminateMessage`, оно добавляет необходимые утверждения, чтобы показать, что служба поддерживает дополнительные действия обмена сообщениями для завершения сеанса. Клиенты могут использовать это действие. В следующем коде WSDL показаны утверждения политики, созданные на базе элемента `HttpCookieSessionBindingElement`.  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Класс `HttpCookieSessionBinding` является предоставляемой системой привязкой, которая использует описанный выше элемент привязки.  
  
## <a name="adding-the-channel-to-the-configuration-system"></a>Добавление канала в систему конфигурации  
 В этом образце имеется два канала, делающие канал доступным через конфигурацию. Первый - элемент <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> для `HttpCookieSessionBindingElement`. Основная часть реализации делегируется классу `HttpCookieSessionBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>. Элемент `HttpCookieSessionBindingConfigurationElement` имеет свойства, которые соответствуют свойствам элемента `HttpCookieSessionBindingElement`.  
  
### <a name="binding-element-extension-section"></a>Раздел расширения элемента привязки  
 Разделе `HttpCookieSessionBindingElementSection` — <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> , предоставляющий `HttpCookieSessionBindingElement` системе конфигурации. С помощью нескольких простых переопределений определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки. Мы можем затем зарегистрировать раздел расширения в файле конфигурации следующим образом.  
  
```xml  
<configuration>        
    <system.serviceModel>        
      <extensions>          
        <bindingElementExtensions>            
          <add name="httpCookieSession"   
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,   
                    HttpCookieSessionExtension, Version=1.0.0.0,   
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>        
    </system.serviceModel>    
</configuration>  
```  
  
## <a name="test-code"></a>Тестовый код  
 Тестовый код для использования этого примера транспорта находится в каталогах Client и Service. Он состоит из двух тестов-один тест использует привязку с `allowCookies` присвоено `true` на стороне клиента. Второй тест включает на привязке явное отключение (с помощью обмена сообщениями завершения).  
  
 При запуске примера результат должен выглядеть следующим образом:  
  
```  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Установка ASP.NET 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
