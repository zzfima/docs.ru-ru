---
title: "Передача по элементу тела сообщения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Передача по элементу тела сообщения
В образце демонстрируется реализация альтернативного алгоритма для присвоения операциям входящих сообщений.  
  
 По умолчанию диспетчер модели службы выбирает соответствующий метод обработки для входящего сообщения, основанный на заголовке "Действие" механизма WS\-Addressing сообщения или аналогичной информации запроса HTTP SOAP.  
  
 Некоторые стеки веб\-служб SOAP 1.1 не соответствуют рекомендациям WS\-I Basic Profile 1.1, поэтому не распределяют сообщения, основываясь не на URI действия, а на полном XML\-имени первого элемента внутри тела SOAP.  Аналогично, клиентская сторона этих стеков может отправлять сообщения с пустым или произвольным заголовком HTTP SoapAction, который разрешен спецификацией SOAP 1.1.  
  
 Чтобы изменить способ отправки сообщений методам, образец реализует интерфейс расширения <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> для события `DispatchByBodyElementOperationSelector`.  Этот класс выбирает операции, основываясь на первом элементе тела сообщения.  
  
 Конструктор класса ожидает словарь, который заполняется парами `XmlQualifiedName` и строками, в котором полные имена указывают имя первого дочернего элемента тела SOAP, а строки указывают на имя соответствующей операции.  `defaultOperationName` \- это имя операции, которая принимает все сообщения, которые не были найдены в этом словаре.  
  
```  
class DispatchByBodyElementOperationSelector : IDispatchOperationSelector  
{  
    Dictionary<XmlQualifiedName, string> dispatchDictionary;  
    string defaultOperationName;  
  
    public DispatchByBodyElementOperationSelector(Dictionary<XmlQualifiedName,string> dispatchDictionary, string defaultOperationName)  
    {  
        this.dispatchDictionary = dispatchDictionary;  
        this.defaultOperationName = defaultOperationName;  
    }  
```  
  
 Реализации <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> являются очень простыми в построении, так как есть только один метод в интерфейсе: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.  Этот метод отвечает за проверку входящих сообщений и возврат строки, которая равна имени метода контракта службы для текущей конечной точки.  
  
 В этом образце селектор операций приобретает класс <xref:System.Xml.XmlDictionaryReader> для тела входящего сообщения, используя метод <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.  Этот метод уже расположил средство чтения на первом дочернем элементе тела сообщения, поэтому достаточно получить имя текущего элемента, универсальный код ресурса \(URI\) пространства имен и объединить их в `XmlQualifiedName`, чтобы затем использовать для поиска соответствующей операции в словаре, хранящемся в селекторе операций.  
  
```  
public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
{  
    XmlDictionaryReader bodyReader = message.GetReaderAtBodyContents();  
    XmlQualifiedName lookupQName = new  
       XmlQualifiedName(bodyReader.LocalName, bodyReader.NamespaceURI);  
    message = CreateMessageCopy(message,bodyReader);  
    if (dispatchDictionary.ContainsKey(lookupQName))  
    {  
         return dispatchDictionary[lookupQName];  
    }  
    else  
    {  
        return defaultOperationName;  
    }  
}  
```  
  
 Доступ к телу сообщения с помощью метода <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> или любого другого метода, который обеспечивает доступ к содержимому тела сообщения, приводит к тому, что сообщение помечается как "read", то есть дальнейшая обработка сообщения является недопустимой.  Поэтому селектор операций создает копию входящего сообщения с помощью метода, который показан в следующем коде.  Поскольку позиция средства чтения не изменялась во время проверки, новое созданное сообщение может ссылаться на нее. В это сообщение также копируются свойства и заголовки сообщения, результаты которого являются точной копией исходного сообщения.  
  
```  
  
private Message CreateMessageCopy(Message message,   
                                     XmlDictionaryReader body)  
{  
    Message copy = Message.CreateMessage(message.Version,message.Headers.Action,body);  
    copy.Headers.CopyHeaderFrom(message,0);  
    copy.Properties.CopyProperties(message.Properties);  
    return copy;  
}  
  
```  
  
## Добавление селектора операции в службу  
 Селекторы службы операции отправки являются расширениями для диспетчера [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  Для выбранных методов на канале обратного вызова дуплексных контрактов также есть селекторы операций клиента, которые работают схоже с описанными здесь селекторами операции отправки, но которые не представлены в этом образце в явном виде.  
  
 Подобно большинству расширений моделей служб, селекторы операций отправки добавляются диспетчеру с использованием поведения.  *Поведение* является объектом конфигурации, который либо добавляет одно или несколько расширений для среды выполнения распределения \(или для среды выполнения клиента\), либо, в противном случае, изменяет его параметры.  
  
 Поскольку селекторы операций имеют область контрактов, реализуется поведение <xref:System.ServiceModel.Description.IContractBehavior>.  Поскольку интерфейс реализован для производного класса <xref:System.Attribute>, как показано в коде, поведение может быть добавлено декларативно в любой контракт службы.  Если класс <xref:System.ServiceModel.ServiceHost> уже открыт и среда выполнения распределения построена, все поведение, обнаруженное в качестве атрибутов в контрактах, операциях и реализациях служб или в качестве элемента в конфигурации службы, автоматически добавляется и впоследствии запрашивается для участия в расширениях или изменении конфигурации по умолчанию.  
  
 Для краткости следующий фрагмент кода показывает только реализацию метода <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, который оказывает результирующее воздействие на изменение конфигурации для диспетчера в этом образце.  Другие методы не показаны, поскольку они возвращаются вызывающему объекту без выполнения какой\-либо работы.  
  
```  
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)   
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 Реализация метода <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> настраивает словарь поиска для селектора операций путем итераций среди элементов класса <xref:System.ServiceModel.Description.OperationDescription> в конечной точке службы <xref:System.ServiceModel.Description.ContractDescription>.  Затем каждое описание операции проверяется на присутствие поведения `DispatchBodyElementAttribute` и реализации интерфейса <xref:System.ServiceModel.Description.IOperationBehavior>, который тоже определен в этом образце.  До тех пор пока этот класс является поведением, он пассивен и не принимает активного участия в изменении конфигурации среды времени выполнения.  Любой из его методов возвращается вызывающему объекту без выполнения каких\-либо действий.  Существует только поведение операции; в результате могут быть ассоциированы с соответствующими операциями только метаданные, необходимые для нового механизма диспетчеризации \- полное имя элемента тела, на котором выбрано вхождение операции.  
  
 Если такое поведение найдено, создается пара значений "полное XML\-имя" \(свойство `QName`\) и "имя операции" \(свойство `Name`\), которая добавляется в словарь.  
  
 Как только словарь заполняется, с использованием этой информации строится новый селектор `DispatchByBodyElementOperationSelector` и задается как селектор операций для данной среды выполнения распределения.  
  
```  
public void ApplyDispatchBehavior(ContractDescription contractDescription, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatchRuntime)  
{  
    Dictionary<XmlQualifiedName,string> dispatchDictionary =   
                     new Dictionary<XmlQualifiedName,string>();  
    foreach( OperationDescription operationDescription in   
                              contractDescription.Operations )  
    {  
        DispatchBodyElementAttribute dispatchBodyElement =   
   operationDescription.Behaviors.Find<DispatchBodyElementAttribute>();  
        if ( dispatchBodyElement != null )  
        {  
             dispatchDictionary.Add(dispatchBodyElement.QName,   
                              operationDescription.Name);  
        }  
    }  
    dispatchRuntime.OperationSelector =   
            new DispatchByBodyElementOperationSelector(  
               dispatchDictionary,   
               dispatchRuntime.UnhandledDispatchOperation.Name);  
    }  
}  
```  
  
## Реализация службы  
 Реализованное в этом образце поведение непосредственно влияет на то, как сообщения из канала связи интерпретируется и отправляется, что является функцией контракта службы.  В результате поведение должно быть объявлено на уровне контракта службы в реализации любой службы, которая выбирает его для своего использования.  
  
 Образец службы проекта применяет поведение контракта `DispatchByBodyElementBehaviorAttribute` к контракту службы `IDispatchedByBody` `OperationForBodyA()` и `OperationForBodyB()` атрибутом поведения операции `DispatchBodyElementAttribute`.  Когда открыт узел службы, который реализует этот контракт, эти метаданные используются конструктором диспетчера в соответствии с приведенным описанием.  
  
 Поскольку селектор операции при направлении принимает во внимание только элемент тела сообщений и игнорирует заголовок "Действие", требуется указать среде выполнения не проверять заголовок "Действие" возвращаемых ответов путем присвоения подстановочного знака "\*" свойству `ReplyAction` класса <xref:System.ServiceModel.OperationContractAttribute>.  Более того, необходимо иметь операцию по умолчанию, у которой свойству "Действие" присвоен подстановочный знак "\*".  Операция по умолчанию получает все сообщения, которые не могут быть отправлены и не имеют `DispatchBodyElementAttribute`.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
                            DispatchByBodyElementBehavior]  
public interface IDispatchedByBody  
{  
    [OperationContract(ReplyAction="*"),   
     DispatchBodyElement("bodyA","http://tempuri.org")]  
    Message OperationForBodyA(Message msg);  
    [OperationContract(ReplyAction = "*"),   
     DispatchBodyElement("bodyB", "http://tempuri.org")]  
    Message OperationForBodyB(Message msg);  
    [OperationContract(Action="*", ReplyAction="*")]  
    Message DefaultOperation(Message msg);  
}  
```  
  
 Реализация образца службы очень проста.  Каждый метод упаковывает принятое сообщение в сообщение ответа и возвращает его обратно клиенту.  
  
## Построение и запуск образца  
 При выполнении образца содержимое тела ответов операции отображается в окне консоли клиента аналогично приведенному \(форматированному\) результату работы.  
  
 Клиент отправляет службе три сообщения с элементами содержимого тела `bodyA`, `bodyB` и `bodyX` соответственно.  Как отложилось из предыдущего описания и как показывает контракт службы, входящее сообщение с элементом `bodyA` отправляется методу `OperationForBodyA()`.  Поскольку отсутствует явный целевой объект, чтобы определить сообщение с телом элемента `bodyX`, сообщение отправляется операции `DefaultOperation()`.  Каждая из операций службы упаковывает полученное тело сообщения в элемент для данного метода и возвращает его. Это сделано для четкой корреляции входных и сообщений для этого образца.  
  
```  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyA xmlns="http://tempuri.org">  
   <q:bodyA xmlns:q="http://tempuri.org">test</q:bodyA>  
</replyBodyA>  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyB xmlns="http://tempuri.org">  
  <q:bodyB xmlns:q="http://tempuri.org">test</q:bodyB>  
</replyBodyB>  
<?xml version="1.0" encoding="IBM437"?>  
<replyDefault xmlns="http://tempuri.org">  
   <q:bodyX xmlns:q="http://tempuri.org">test</q:bodyX>  
</replyDefault>  
  
```  
  
#### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Для сборки решения следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
  
## См. также