---
title: Модуль форматирования и селектор операции
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: 8653bfd12df8eaf422797197cfcc58e9a46274bf
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424294"
---
# <a name="operation-formatter-and-operation-selector"></a>Модуль форматирования и селектор операции
В этом образце показано, как можно использовать точки расширяемости Windows Communication Foundation (WCF) для предоставления данных сообщений в формате, отличном от того, который требуется WCF. По умолчанию модули форматирования WCF предполагают включение параметров метода в элемент `soap:body`. В этом образце показано, как реализовать пользовательский модуль форматирования операций, который анализирует параметры из строки HTTP-запроса GET и вызывает методы с использованием этих данных.  
  
 Образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует контракт службы `ICalculator`. Он показывает, каким образом можно изменить сообщения Add, Subtract, Multiply и Divide, чтобы они использовали HTTP-запросы GET в качестве запросов клиента серверу и HTTP-запросы POST с сообщениями POX в качестве ответов сервера клиенту.  
  
 Для этого в образце имеются следующие элементы.  
  
- Класс `QueryStringFormatter`, который реализует интерфейсы <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> и <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> для клиента и сервера соответственно и обрабатывает данные в строке запроса.  
  
- Класс `UriOperationSelector`, который реализует интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> на сервере для выполнения диспетчеризации операций в зависимости от имени операции в запросе GET.  
  
- Поведение конечной точки `EnableHttpGetRequestsBehavior` (и соответствующая конфигурация), которое добавляет в среду выполнения селектор нужной операции.  
  
- Показано, как включить в среду выполнения новый модуль форматирования операций.  
  
- В этом образце служба и клиент являются консольными приложениями (EXE).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="key-concepts"></a>Основные понятия  
 `QueryStringFormatter` — модуль форматирования операций — это компонент в WCF, который отвечает за преобразование сообщения в массив объектов параметров и массив объектов параметров в сообщение. Эта задача выполняется на клиенте с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> и на сервере с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>. Эти интерфейсы позволяют пользователям получать сообщения запросов и ответов из методов `Serialize` и `Deserialize`.  
  
 В этом образце класс `QueryStringFormatter` реализует оба эти интерфейса и реализуется на стороне клиента и сервера.  
  
 Запрос  
  
- В этом образце класс <xref:System.ComponentModel.TypeConverter> используется для преобразования параметров в сообщении запроса в строки и обратно. Если объект для определенного типа <xref:System.ComponentModel.TypeConverter> недоступен, модуль форматирования в этом образце создает исключение.  
  
- В методе `IClientMessageFormatter.SerializeRequest` на стороне клиента модуль форматирования создает код URI для соответствующего адреса назначения и добавляет имя операции в качестве суффикса. Это имя используется для перенаправления на соответствующую операцию на сервере. После этого массив объектов параметров сериализуется в строку запроса кода URI с использованием имен и значений параметров, преобразованных классом <xref:System.ComponentModel.TypeConverter>. Свойства <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> и <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> задаются данному URI. Значение <xref:System.ServiceModel.Channels.MessageProperties> доступно через свойство <xref:System.ServiceModel.Channels.Message.Properties%2A>.  
  
- В методе `IDispatchMessageFormatter.DeserializeRequest` на сервере модуль форматирования извлекает код URI `Via` в свойствах сообщения входящего запроса. Модуль форматирования преобразует пары "имя-значение" в строке запроса URI в имена и значения параметров и подставляет эти имена и значения параметров в массив передаваемых методу параметров. Обратите внимание, что диспетчеризация по операциям уже произошла, поэтому в данном методе суффикс имени операции игнорируется.  
  
 Ответ  
  
- В этом образце HTTP-метод GET используется только для запросов. Модуль форматирования делегирует отправку ответа исходному модулю форматирования, который бы использовался для создания XML-сообщения. Одна из целей этого образца заключается в том, чтобы показать, как можно реализовать такой делегирующий модуль форматирования.  
  
### <a name="uripathsuffixoperationselector-class"></a>Класс UriPathSuffixOperationSelector  
 Интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> позволяет пользователям реализовывать собственную логику определения операции, которой должно перенаправляться то или иное сообщение.  
  
 В этом образце необходимо реализовать на сервере класс `UriPathSuffixOperationSelector`, чтобы выбирать нужную операцию, поскольку имя операции включается в код URI HTTP-запроса GET, а не в заголовок действия в сообщении. В этом образце разрешены только имена операций, указываемые с учетом регистра.  
  
 Метод `SelectOperation` принимает входящее сообщение и ищет в свойствах сообщения код URI `Via`. Он извлекает из кода URI суффикс имени операции, ищет во внутренней таблице имя операции, которой следует перенаправить сообщение, и возвращает имя операции.  
  
### <a name="enablehttpgetrequestsbehavior-class"></a>Класс EnableHttpGetRequestsBehavior  
 Компонент `UriPathSuffixOperationSelector` можно настраивать программным образом или с помощью поведения конечной точки. В этом образце реализовано поведение `EnableHttpGetRequestsBehavior`, которое задано в файле конфигурации приложения службы.  
  
 На сервере:  
  
 Свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> присвоена реализация <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.  
  
 По умолчанию WCF использует фильтр адресов точного соответствия. Код URI входящего сообщения содержит суффикс имени операции, за которым следует строка запроса, содержащая данные параметров, поэтому поведение также изменяет фильтр адресов, чтобы он срабатывал по совпадению префикса. Для этой цели используется<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> WCF.  
  
### <a name="installing-operation-formatters"></a>Установка модулей форматирования операций  
 Поведения операций, которые задают модули форматирования, являются уникальными. Одно такое поведение всегда реализуется по умолчанию для каждой операции, чтобы создать нужный модуль форматирования операции. Однако такие поведения очень похожи на поведения других операций; их невозможно идентифицировать по каким-либо другим атрибутам. Чтобы установить поведение при замене, реализация должна найти определенные поведения модуля форматирования, которые устанавливаются загрузчиком типов WCF по умолчанию, и либо заменить его, либо добавить совместимое поведение для запуска после поведения по умолчанию.  
  
 Эти поведения модулей форматирования операций можно задать программным образом перед вызовом <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> или путем задания поведения операции, которое выполняется после поведения по умолчанию. Однако его невозможно легко настроить с помощью поведения конечной точки (а следовательно с помощью конфигурации), поскольку модель поведений не допускает замены поведения другими поведениями или иного изменения дерева описаний.  
  
 На клиенте:  
  
 Реализацию <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> нужно осуществлять таким образом, чтобы этот модуль форматирования мог преобразовывать запросы в HTTP-запросы GET и делегировать создание ответов исходному модулю форматирования. Для этого вызывается вспомогательный метод `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`.  
  
 Это необходимо сделать до вызова метода `CreateChannel`.  
  
```csharp  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 На сервере:  
  
- Интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> нужно реализовать таким образом, чтобы этот модуль форматирования мог считывать HTTP-запросы GET и делегировать создание ответов исходному модулю форматирования. Это делается путем вызова того же вспомогательного метода `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`, что и для клиента (см. предыдущий пример кода).  
  
- Это необходимо сделать до вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. В этом образце показано, каким образом можно вручную изменить модуль форматирования перед вызовом метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Того же результата можно достичь, создав для класса <xref:System.ServiceModel.ServiceHost> производный класс, который вызывает `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` перед открытием (примеры см. в документации по размещению).  
  
### <a name="user-experience"></a>Взаимодействие с пользователем  
 На сервере:  
  
- Серверную реализацию `ICalculator` изменять не требуется.  
  
- В файле App.config службы следует задавать пользовательскую привязку POX, которая устанавливает для атрибута `messageVersion` элемента `textMessageEncoding` значение `None`.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- Кроме того, в файле App.config службы необходимо задать пользовательское поведение `EnableHttpGetRequestsBehavior`, добавив его в раздел расширений поведения.  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add   
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
- Перед вызовом метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> необходимо добавить модули форматирования операций.  
  
 На клиенте:  
  
- Изменять клиентскую реализацию не требуется.  
  
- В файле App.config клиента следует задать пользовательскую привязку POX, которая устанавливает для атрибута `messageVersion` элемента `textMessageEncoding` значение `None`. Отличие от службы заключается в том, что клиент должен включить ручную адресацию, чтобы можно было изменять исходящий адрес назначения.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- В файле App.config клиента должно быть задано то же пользовательское поведение `EnableHttpGetRequestsBehavior`, что и на сервере.  
  
- Перед вызовом метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel> необходимо добавить модули форматирования операций.  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Все четыре операции (Add, Subtract, Multiply и Divide) должны выполняться успешно.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
