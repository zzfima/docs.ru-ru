---
title: Инспекторы сообщений
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 29c7fd9729cbdcc99a05d01f717c1cc548e8d9ea
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714828"
---
# <a name="message-inspectors"></a>Инспекторы сообщений
В этом образце демонстрируется, как реализовать и настроить инспекторы сообщений клиента и службы.  
  
 Инспектор сообщений - это объект расширяемости, который можно использовать программно или посредством конфигурации в среде выполнения клиента модели служб и среде выполнения распределения для проверки и изменения сообщений перед их получением или отправкой.  
  
 В этом образце реализуется базовый механизм проверки сообщений клиента и службы, который проверяет входящие сообщения на основе набора настраиваемых документов XML-схемы. Обратите внимание, что в этом образце сообщения проверяются не для всех операций. Данное упрощение сделано преднамеренно.  
  
## <a name="message-inspector"></a>Инспектор сообщений  
 Инспекторы сообщений клиента реализуют интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>, а инспекторы сообщений службы - интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>. Реализации можно объединить в один класс для создания инспектора сообщений, работающего на обеих сторонах. В данном образце реализуется такой комбинированный инспектор сообщений. Инспектор создается, передавая набор схем, на основе которых проверяются входящие и исходящие сообщения, и позволяет разработчику определить, следует ли проверять входящие или исходящие сообщения, а также использовать ли режим диспетчеризации или режим клиента, который влияет на обработку ошибок, как описано далее в этом разделе.  
  
```csharp
public class SchemaValidationMessageInspector : IClientMessageInspector, IDispatchMessageInspector  
{  
    XmlSchemaSet schemaSet;  
    bool validateRequest;  
    bool validateReply;  
    bool isClientSide;  
    [ThreadStatic]  
    bool isRequest;  
  
    public SchemaValidationMessageInspector(XmlSchemaSet schemaSet,  
         bool validateRequest, bool validateReply, bool isClientSide)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = validateReply;  
        this.validateRequest = validateRequest;  
        this.isClientSide = isClientSide;  
    }  
```  
  
 Любой инспектор сообщений службы (диспетчера) должен реализовывать два метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>: <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> и <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.  
  
 Метод <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> вызывается диспетчером при получении сообщения, обработке сообщения стеком каналов и назначении сообщения службе, но перед его десериализацией и отправкой операции. Если входящее сообщение было зашифровано, оно поступает в инспектор сообщений в расшифрованном виде. Метод получает сообщение `request`, переданное в качестве ссылочного параметра, который позволяет проверить, изменить или заменить сообщение при необходимости. Возвращаемое значение может быть любым объектом и используется как объект состояния корреляции, передаваемый методу <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> при возврате службой ответа на текущее сообщение. В этом образце метод <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> делегирует проверку сообщения закрытому локальному методу `ValidateMessageBody` и не возвращает объект состояния корреляции. Этот метод гарантирует, что службе не будут передаваться недопустимые сообщения.  
  
```csharp  
object IDispatchMessageInspector.AfterReceiveRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel, System.ServiceModel.InstanceContext instanceContext)  
{  
    if (validateRequest)  
    {  
        // inspect the message. If a validation error occurs,  
        // the thrown fault exception bubbles up.  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 Метод <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> вызывается, когда ответ готов для отправки клиенту или, в случае односторонних сообщений, после обработки входящего сообщения. Это позволяет симметрично вызывать необходимые расширения независимо от шаблона обмена сообщениями. Как и в случае метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, сообщение передается в качестве ссылочного параметра и может быть проверено, изменено или заменено. Проверка сообщения, выполняемая в этом образце, повторно делегируется методу `ValidMessageBody`, но в данном случае процедура обработки ошибок проверки немного отличается.  
  
 При возникновении ошибки проверки метод `ValidateMessageBody` вызывает исключения, унаследованные от <xref:System.ServiceModel.FaultException>. В случае метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> эти исключения могут размещаться в инфраструктуре модели служб, где они автоматически преобразуются в ошибки SOAP и передаются клиенту. В случае метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> исключения <xref:System.ServiceModel.FaultException> не следует размещать в инфраструктуре, поскольку преобразование исключений ошибок, вызванных службой, происходит перед вызовом инспектора сообщений. Поэтому следующая реализация перехватывает известное исключение `ReplyValidationFault` и заменяет ответное сообщение явным сообщением об ошибке. Этот метод гарантирует, что реализацией службы не будут возвращаться недопустимые сообщения.  
  
```csharp  
void IDispatchMessageInspector.BeforeSendReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        // Inspect the reply, catch a possible validation error   
        try  
        {  
            ValidateMessageBody(ref reply, false);  
        }  
        catch (ReplyValidationFault fault)  
        {  
            // if a validation error occurred, the message is replaced  
            // with the validation fault.  
            reply = Message.CreateMessage(reply.Version,   
                    fault.CreateMessageFault(), reply.Headers.Action);  
        }  
    }  
```  
  
 Инспектор сообщений клиента очень похож на инспектор сообщений службы. На основе <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> необходимо реализовать два метода: <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> и <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.  
  
 Метод <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> вызывается при создании сообщения клиентским приложением или модулем форматирования операций. Как и в случае инспекторов сообщений диспетчера, сообщение может быть просто проверено или полностью заменено. В этом образце инспектор выполняет делегирование тому же локальному вспомогательному методу `ValidateMessageBody`, который используется для инспекторов сообщений диспетчера.  
  
 Различие в поведении между проверкой клиента и службы (как указано в конструкторе) заключается в том, что проверка клиента вызывает локальные исключения, которые размещаются в пользовательском коде, поскольку они возникают локально и не по причине сбоя службы. Как правило, инспекторы диспетчера службы выдают сообщения об ошибках, а инспекторы клиента - исключения.  
  
 Эта реализация <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> гарантирует, что службе не будут передаваться недопустимые сообщения.  
  
```csharp  
object IClientMessageInspector.BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
{  
    if (validateRequest)  
    {  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 Реализация `AfterReceiveReply` гарантирует, что полученные от службы недопустимые сообщения не будут передаваться пользовательскому коду клиента.  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 Ключевым элементом данного инспектора сообщений является метод `ValidateMessageBody`. Для выполнения работы он обертывает проверяющее средство чтения <xref:System.Xml.XmlReader> вокруг поддерева содержимого тела переданного сообщения. Средство чтения заполняется набором схем, которые содержит инспектор сообщений, и обратный вызов проверки настраивается на делегат, относящийся к обработчику `InspectionValidationHandler`, который определен наряду с данным методом. Для выполнения проверки сообщение считывается и буферизуется в поддерживаемом потоком памяти объекте <xref:System.Xml.XmlDictionaryWriter>. При возникновении ошибки или предупреждения в процессе проверки вызывается метод обратного вызова.  
  
 При отсутствии ошибок создается новое сообщение, копирующее свойства и заголовки из исходного сообщения и использующее уже проверенный набор сведений в потоке памяти, который обернут объектом <xref:System.Xml.XmlDictionaryReader> и добавлен в заменяющее сообщение.  
  
```csharp  
void ValidateMessageBody(ref System.ServiceModel.Channels.Message message, bool isRequest)  
{  
    if (!message.IsFault)  
    {  
        XmlDictionaryReaderQuotas quotas =   
                new XmlDictionaryReaderQuotas();  
        XmlReader bodyReader =   
            message.GetReaderAtBodyContents().ReadSubtree();  
        XmlReaderSettings wrapperSettings =   
                              new XmlReaderSettings();  
        wrapperSettings.CloseInput = true;  
        wrapperSettings.Schemas = schemaSet;  
        wrapperSettings.ValidationFlags =   
                                XmlSchemaValidationFlags.None;  
        wrapperSettings.ValidationType = ValidationType.Schema;  
        wrapperSettings.ValidationEventHandler += new   
           ValidationEventHandler(InspectionValidationHandler);  
        XmlReader wrappedReader = XmlReader.Create(bodyReader,   
                                            wrapperSettings);  
  
        // pull body into a memory backed writer to validate  
        this.isRequest = isRequest;  
        MemoryStream memStream = new MemoryStream();  
        XmlDictionaryWriter xdw =  
              XmlDictionaryWriter.CreateBinaryWriter(memStream);  
        xdw.WriteNode(wrappedReader, false);  
        xdw.Flush(); memStream.Position = 0;  
        XmlDictionaryReader xdr =   
        XmlDictionaryReader.CreateBinaryReader(memStream, quotas);  
  
        // reconstruct the message with the validated body  
        Message replacedMessage =   
            Message.CreateMessage(message.Version, null, xdr);  
        replacedMessage.Headers.CopyHeadersFrom(message.Headers);  
        replacedMessage.Properties.CopyProperties(message.Properties);  
        message = replacedMessage;  
    }  
}  
```  
  
 Метод `InspectionValidationHandler` вызывается проверяющим объектом <xref:System.Xml.XmlReader> при каждом возникновении ошибки или предупреждения проверки схемы. Следующая реализация работает только с ошибками и не учитывает все предупреждения.  
  
 При первом рассмотрении может показаться возможной вставка проверяющего объекта <xref:System.Xml.XmlReader> в сообщение с инспектором сообщений, чтобы проверка происходила по мере обработки сообщения без его буферизации. Однако это означает, что по мере обнаружения недопустимых XML-узлов данный обратный вызов создает исключения проверки в некоторой области инфраструктуры модели служб или пользовательского кода, приводящие к непредсказуемому поведению. Подход на основе буферизации полностью ограждает пользовательский код от недопустимых сообщений.  
  
 Как отмечалось ранее, исключения, вызываемые обработчиком на стороне клиента и на стороне службы различаются. На стороне службы исключения наследуются от <xref:System.ServiceModel.FaultException>, на стороне клиента исключения являются регулярными пользовательскими исключениями.  
  
```csharp  
        void InspectionValidationHandler(object sender, ValidationEventArgs e)  
{  
    if (e.Severity == XmlSeverityType.Error)  
    {  
        // We are treating client and service side validation errors  
        // differently here. Client side errors cause exceptions  
        // and are thrown straight up to the user code. Service side  
        // validations cause faults.  
        if (isClientSide)  
        {  
            if (isRequest)  
            {  
                throw new RequestClientValidationException(e.Message);  
            }  
            else  
            {  
                throw new ReplyClientValidationException(e.Message);  
            }  
        }  
        else  
        {  
            if (isRequest)  
            {  
                // this fault is caught by the ServiceModel   
                // infrastructure and turned into a fault reply.  
                throw new RequestValidationFault(e.Message);  
             }  
             else  
             {  
                // this fault is caught and turned into a fault message  
                // in BeforeSendReply in this class  
                throw new ReplyValidationFault(e.Message);  
              }  
          }  
      }  
    }  
```  
  
## <a name="behavior"></a>Поведение  
 Инспекторы сообщений являются расширениями среды выполнения клиента или среды выполнения распределения. Такие расширения настраиваются с помощью *поведений*. Поведение - это класс, изменяющий поведение среды выполнения модели служб путем изменения конфигурации по умолчанию или добавления в нее расширений (например, инспекторов сообщений).  
  
 Следующий класс `SchemaValidationBehavior` является поведением, которое используется для добавления инспектора сообщений, создаваемого в данном образце, в среду выполнения клиента или среду выполнения распределения. В обоих случаях реализация достаточно проста. В случае <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> и <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A> инспектор сообщений создается и добавляется в коллекцию <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> соответствующей среды выполнения.  
  
```csharp
public class SchemaValidationBehavior : IEndpointBehavior  
{  
    XmlSchemaSet schemaSet;   
    bool validateRequest;   
    bool validateReply;  
  
    public SchemaValidationBehavior(XmlSchemaSet schemaSet, bool   
                           inspectRequest, bool inspectReply)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = inspectReply;  
        this.validateRequest = inspectRequest;  
    }  
    #region IEndpointBehavior Members  
  
    public void AddBindingParameters(ServiceEndpoint endpoint,   
       System.ServiceModel.Channels.BindingParameterCollection   
                                            bindingParameters)  
    {  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint,   
            System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
    {  
        SchemaValidationMessageInspector inspector =   
           new SchemaValidationMessageInspector(schemaSet,   
                      validateRequest, validateReply, true);  
            clientRuntime.MessageInspectors.Add(inspector);  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint,   
         System.ServiceModel.Dispatcher.EndpointDispatcher   
                                          endpointDispatcher)  
    {  
        SchemaValidationMessageInspector inspector =   
           new SchemaValidationMessageInspector(schemaSet,   
                        validateRequest, validateReply, false);  
   endpointDispatcher.DispatchRuntime.MessageInspectors.Add(inspector);  
    }  
  
   public void Validate(ServiceEndpoint endpoint)  
   {  
   }  
  
    #endregion  
}  
```  
  
> [!NOTE]
> Данное конкретное поведение не дублируется как атрибут, поэтому его нельзя декларативно добавить в тип контракта типа службы. Это решение было принято намеренно, поскольку коллекцию схем нельзя загрузить в объявление атрибута, а обращение к размещению дополнительной конфигурации (например, к параметрам приложения) в этом атрибуте означает создание элемента конфигурации, не согласованного с остальной конфигурацией модели служб. Поэтому данное поведение можно добавить только императивно посредством кода и посредством расширения конфигурации модели служб.  
  
## <a name="adding-the-message-inspector-through-configuration"></a>Добавление инспектора сообщений с помощью конфигурации  
 Для настройки пользовательского поведения в конечной точке в файле конфигурации приложения модели службы требуются разработчики для создания *элемента расширения* конфигурации, представленного классом, производным от <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>. Это расширение затем необходимо добавить в раздел конфигурации модели служб для расширений, как показано для следующего расширения, рассматриваемого в данном разделе.  
  
```xml  
<system.serviceModel>  
…  
   <extensions>  
      <behaviorExtensions>  
        <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
      </behaviorExtensions>  
    </extensions>  
…  
</system.serviceModel>  
```  
  
 Расширения можно добавить в файл конфигурации приложения или ASP.NET, что является наиболее распространенным вариантом, либо в файл конфигурации компьютера.  
  
 При добавлении расширения в область конфигурации можно добавить поведение в конфигурацию поведения, как показано в следующем коде. Конфигурации поведения являются элементами многократного использования, которые можно по мере необходимости применять к нескольким конечным точкам. Поскольку настраиваемое здесь конкретное поведение реализует интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, оно допустимо только в соответствующем разделе файла конфигурации.  
  
```xml  
<system.serviceModel>  
   <behaviors>  
      …  
     <endpointBehaviors>  
        <behavior name="HelloServiceEndpointBehavior">  
          <schemaValidator validateRequest="True" validateReply="True">  
            <schemas>  
              <add location="messages.xsd" />    
            </schemas>  
          </schemaValidator>  
        </behavior>  
      </endpointBehaviors>  
      …  
    </behaviors>  
</system.serviceModel>  
```  
  
 Элемент `<schemaValidator>`, настраивающий инспектор сообщений, поддерживается классом `SchemaValidationBehaviorExtensionElement`. Класс предоставляет два открытых свойства логического типа: `ValidateRequest` и `ValidateReply`. Оба свойства отмечены атрибутом <xref:System.Configuration.ConfigurationPropertyAttribute>. Этот атрибут представляет собой связь между свойствами кода и XML-атрибутами, которые можно увидеть заданными для предыдущего XML-элемента конфигурации. Кроме того, в классе имеется свойство `Schemas`, дополнительно отмеченное атрибутом <xref:System.Configuration.ConfigurationCollectionAttribute> и принадлежащее к типу `SchemaCollection`, которое также является частью этого образца, но исключено из данного документа для краткости изложения. Это свойство вместе с коллекцией и классом элемента коллекции `SchemaConfigElement` поддерживает элемент `<schemas>` в предыдущем фрагменте конфигурации и позволяет добавить коллекцию схем в набор проверки.  
  
 Переопределенный метод `CreateBehavior` преобразует данные конфигурации в объект поведения при их оценке средой выполнения во время построения клиента или конечной точки.  
  
```csharp
public class SchemaValidationBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public SchemaValidationBehaviorExtensionElement()  
    {  
    }  
  
    public override Type BehaviorType   
    {   
        get  
        {  
            return typeof(SchemaValidationBehavior);  
        }   
    }  
  
    protected override object CreateBehavior()  
    {  
        XmlSchemaSet schemaSet = new XmlSchemaSet();  
        foreach (SchemaConfigElement schemaCfg in this.Schemas)  
        {  
            Uri baseSchema = new   
                Uri(AppDomain.CurrentDomain.BaseDirectory);  
            string location = new   
                Uri(baseSchema,schemaCfg.Location).ToString();  
            XmlSchema schema =   
                XmlSchema.Read(new XmlTextReader(location), null);  
            schemaSet.Add(schema);  
        }  
     return new   
     SchemaValidationBehavior(schemaSet,ValidateRequest,ValidateReply);  
    }  
  
[ConfigurationProperty("validateRequest",DefaultValue=false,IsRequired=false)]  
public bool ValidateRequest  
{  
    get { return (bool)base["validateRequest"]; }  
    set { base["validateRequest"] = value; }  
}  
  
[ConfigurationProperty("validateReply", DefaultValue = false, IsRequired = false)]  
        public bool ValidateReply  
        {  
            get { return (bool)base["validateReply"]; }  
            set { base["validateReply"] = value; }  
        }  
  
     //Declare the Schema collection property.  
     //Note: the "IsDefaultCollection = false" instructs   
     //.NET Framework to build a nested section of   
     //the kind <Schema> ...</Schema>.  
    [ConfigurationProperty("schemas", IsDefaultCollection = true)]  
    [ConfigurationCollection(typeof(SchemasCollection),  
        AddItemName = "add",  
        ClearItemsName = "clear",  
        RemoveItemName = "remove")]  
    public SchemasCollection Schemas  
    {  
        get  
        {  
            SchemasCollection SchemasCollection =  
            (SchemasCollection)base["schemas"];  
            return SchemasCollection;  
        }  
    }  
}  
```  
  
## <a name="adding-message-inspectors-imperatively"></a>Императивное добавление инспекторов сообщений  
 Помимо использования атрибутов (что не поддерживается в данном образце по указанной ранее причине) и конфигурации, поведения можно довольно легко добавить в среду выполнения клиента и службы с помощью императивного кода. В данном образце это выполняется в клиентском приложении для тестирования инспектора сообщений клиента. Класс `GenericClient` наследуется от класса <xref:System.ServiceModel.ClientBase%601>, который предоставляет конфигурацию конечной точки пользовательскому коду. Перед неявным открытием клиента конфигурацию конечной точки можно изменить, например, путем добавления поведений, как показано в следующем коде. Добавление поведения на стороне службы в значительной мере аналогично показанному в данном разделе способу, относящемуся к клиенту, и должно выполняться перед открытием узла службы.  
  
```csharp  
try  
{  
    Console.WriteLine("*** Call 'Hello' with generic client, with client behavior");  
    GenericClient client = new GenericClient();  
  
    // Configure client programmatically, adding behavior  
    XmlSchema schema = XmlSchema.Read(new StreamReader("messages.xsd"),   
                                                          null);  
    XmlSchemaSet schemaSet = new XmlSchemaSet();  
    schemaSet.Add(schema);  
    client.Endpoint.Behaviors.Add(new   
                SchemaValidationBehavior(schemaSet, true, true));  
  
    Console.WriteLine("--- Sending valid client request:");  
    GenericCallValid(client, helloAction);  
    Console.WriteLine("--- Sending invalid client request:");  
    GenericCallInvalid(client, helloAction);  
  
    client.Close();  
}  
catch (Exception e)  
{  
    DumpException(e);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
