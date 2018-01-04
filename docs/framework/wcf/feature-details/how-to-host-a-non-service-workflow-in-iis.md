---
title: "Как разместить не являющийся службой рабочий процесс в службах IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362562c-767d-401b-8257-916616568fd4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b7ffdc00a7723fd6b514fbb5577c48da15d719c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a>Как разместить не являющийся службой рабочий процесс в службах IIS
Рабочие процессы, которые не являются службами рабочих процессов, должны быть размещены в службах IIS/WAS. Это может оказаться полезным, если нужно разместить рабочий процесс, разработанный кем-то другим. Например, если необходимо повторно разместить конструктор рабочих процессов и разрешить пользователям создавать собственные рабочие процессы.  Размещение не являющихся службами рабочих процессов в службах IIS обеспечивает поддержку таких функций, как перезапуск процессов, завершение работы при ожидании, наблюдение за работоспособностью процессов и активация на основе сообщений. Службы рабочих процессов, размещенные в службах IIS, содержат действия <xref:System.ServiceModel.Activities.Receive> и активируются в момент получения сообщения службами IIS. Не являющиеся службами рабочие процессы не содержат действий обмена сообщениями и по умолчанию не могут быть активированы отправкой сообщения.  Чтобы создать экземпляр рабочего процесса, необходимо создать класс, производный от <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, и определить контракт службы, содержащий операции. Этот раздел содержит пошаговое руководство по созданию простого рабочего процесса, определение контракта службы, клиент может использовать для активации рабочего процесса и создания класса, производного от класса <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для прослушивания запросов на создание рабочего процесса, которая использует контракт службы.  
  
### <a name="create-a-simple-workflow"></a>Создание простого рабочего процесса  
  
1.  Создайте пустое решение [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с именем `CreationEndpointTest`.  
  
2.  Добавьте в него новый проект служебного приложения рабочего процесса WCF под названием `SimpleWorkflow`. Откроется конструктор рабочих процессов.  
  
3.  Удалите действия ReceiveRequest и SendResponse. Это как раз те действия, которые делают рабочий процесс службой. Поскольку мы не работаем со службами рабочих процессов, они нам не нужны.  
  
4.  Установите свойство DisplayName действия последовательности в значение «Sequential Workflow».  
  
5.  Переименуйте файл Service1.xamlx в Workflow1.xamlx.  
  
6.  Щелкните конструктор за пределами действия последовательности и задайте свойства Name и ConfigurationName для «Workflow1».  
  
7.  Перетащите действие <xref:System.Activities.Statements.WriteLine> в раздел <xref:System.Activities.Statements.Sequence>. <xref:System.Activities.Statements.WriteLine> Действия можно найти в **примитивы** области элементов. Задать <xref:System.Activities.Statements.WriteLine.Text%2A> свойство <xref:System.Activities.Statements.WriteLine> действие «Hello, world».  
  
     После этого рабочий процесс должен выглядеть так, как показано на следующей схеме.  
  
     ![Простой рабочий процесс](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")  
  
### <a name="create-the-workflow-creation-service-contract"></a>Создайте контракт службы создания рабочего процесса  
  
1.  Добавьте новый проект библиотеки классов с названием `Shared` в решение `CreationEndpointTest`.  
  
2.  Добавьте в проект `Shared` ссылки на сборки System.ServiceModel.dll, System.Configuration и System.ServiceModel.Activities.  
  
3.  Переименуйте файл Class1.cs в IWorkflowCreation.cs и вставьте в него следующий код.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     Данный контракт определяет две операции, обе из которых служат для создания нового экземпляра вновь созданного рабочего процесса, не являющегося службой. Один из них создает новый экземпляр с созданием идентификатора экземпляра, а второй позволяет указать идентификатор для нового экземпляра рабочего процесса.  Оба метода позволяют передавать параметры новому экземпляру рабочего процесса. Этот контракт будет доступен через <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> разрешить клиентам для создания новых экземпляров рабочего процесса, не относящиеся к службе.  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a>Создайте класс, производный от WorkflowHostingEndpoint  
  
1.  Добавьте новый класс с именем `CreationEndpoint` производными <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для `Shared` проекта.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  Добавьте локальную статическую переменную типа <xref:System.Uri> с именем `defaultBaseUri` в класс `CreationEndpoint`.  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  Добавьте следующий конструктор в класс `CreationEndpoint`. Обратите внимание, что в вызове конструктора базового класса указан контракт службы `IWorkflowCreation`.  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  Добавьте следующий конструктор по умолчанию в класс `CreationEndpoint`.  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  Добавьте статическое свойство `DefaultBaseUri` в класс `CreationEndpoint`. Это свойство будет использоваться для хранения базового URI по умолчанию, если он не указан.  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  Создайте следующий метод для получения привязки по умолчанию, используемой для конечной точки создания.  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  Переопределите метод <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A>, чтобы он возвращал идентификатор экземпляра рабочего процесса. Если `Action` заголовок заканчивается на «Создать» возвращают пустой идентификатор GUID, если `Action` заголовок заканчивается на «CreateWithInstanceId» возвращают идентификатор GUID, переданный в метод. В противном случае формируется исключение <xref:System.InvalidOperationException>. Эти заголовки `Action` соответствуют двум операциям, определенным в контракте службы `IWorkflowCreation`.  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  Переопределите метод <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A>, чтобы создать <xref:System.ServiceModel.Activities.WorkflowCreationContext> и добавить аргументы для рабочего процесса, отправить клиенту идентификатор экземпляра, а затем вернуть <xref:System.ServiceModel.Activities.WorkflowCreationContext>.  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a>Создайте элемент стандартной конечной точки, чтобы получить возможность настройки WorkflowCreationEndpoint.  
  
1.  Добавьте ссылку на класс Shared в проект `CreationEndpoint`.  
  
2.  Добавьте новый класс с именем `CreationEndpointElement`, производный от <xref:System.ServiceModel.Configuration.StandardEndpointElement>, в проект `CreationEndpoint`. Этот класс будет представлять `CreationEndpoint` в файле web.config.  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  Добавьте свойство `EndpointType`, возвращающее тип конечной точки.  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  Переопределите метод <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> для возврата нового `CreationEndpoint`.  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  Переопределите методы <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> и <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>. Эти методы нужно просто определить, не нужно заполнять их каким-либо кодом.  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  Добавьте класс коллекции для `CreationEndpoint` в файл CreationEndpointElement.cs в проекте `CreationEndpoint`. Этот класс используется конфигурацией для хранения числа экземпляров `CreationEndpoint` в файле web.config.  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  Постройте решение.  
  
### <a name="host-the-workflow-in-iis"></a>Размещение рабочего процесса в службах IIS  
  
1.  Создайте в службах IIS новое приложение с именем `MyCreationEndpoint`.  
  
2.  Скопируйте файл workflow1.xaml, созданный конструктором рабочих процессов, в каталог приложения и переименуйте его в workflow1.xamlx.  
  
3.  Скопируйте файлы shared.dll и CreationEndpoint.dll в каталог bin приложения (создайте этот каталог, если он отсутствует).  
  
4.  Замените содержимое файла Web.config в проекте `CreationEndpoint` следующим кодом.  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  После элемента `<system.web>` зарегистрируйте `CreationEndpoint`, добавив следующий код конфигурации.  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     Этот код зарегистрирует класс `CreationEndpointCollection`, чтобы можно было настроить `CreationEndpoint` в файле web.config.  
  
6.  Добавить `<service>` элемент (после \</extensions > тег) с `CreationEndpoint` который будет прослушивать входящие сообщения.  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  Добавить \<поведения > элемент (после  \< /services > тег) чтобы включить метаданные службы.  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  Скопируйте файл web.config в каталог приложения IIS.  
  
9. Проверьте, работает ли создание конечной точки, запустив Internet Explorer и прейдя по адресу http://localhost/MyCreationEndpoint/Workflow1.xamlx. Internet Explorer должен отобразить следующий экран.  
  
     ![Тестирование службы](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a>Создайте клиента, который будет вызывать CreationEndpoint.  
  
1.  Добавьте новое консольное приложение в решение `CreationEndpointTest`.  
  
2.  Добавьте ссылки на сборки System.ServiceModel.dll, System.ServiceModel.Activities и проект `Shared`.  
  
3.  В `Main` создать метод <xref:System.ServiceModel.ChannelFactory%601> типа `IWorkflowCreation` и вызвать <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Будет возвращена учетная запись-посредник. Затем можно вызвать метод `Create` этой учетной записи-посредника, чтобы создать экземпляр рабочего процесса, размещенного в службах IIS:  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  Запустите приложение CreationEndpointClient. Этот вывод должен выглядеть так:  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  Вывод рабочего процесса не будет отображаться, поскольку он выполняется в службах IIS, не осуществляющих вывода на консоль.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный код для этого образца.  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 Данный пример может показаться неправильным, потому что в нем не реализована служба, реализующая интерфейс `IWorkflowCreation`. Это было автоматически сделано в методе `CreationEndpoint`.  
  
## <a name="see-also"></a>См. также  
 [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Размещение в службах IIS](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Рекомендации по размещению в службах IIS](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Инструкции по размещению в службах IIS](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [Архитектура Windows Workflow Foundation](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [Закладка возобновления для конечной точки WorkflowHostingEndpoint](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [Отдельное размещение конструктора рабочих процессов](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Обзор Windows Workflow Foundation](../../../../docs/framework/windows-workflow-foundation/overview.md)
