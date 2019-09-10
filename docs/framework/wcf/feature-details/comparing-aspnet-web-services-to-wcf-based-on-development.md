---
title: Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: 607d0eaabde4e00c1a00b995356bb6d4e1a39234
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855758"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a>Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки

Windows Communication Foundation (WCF) имеет режим совместимости ASP.NET, позволяющий программировать и настраивать приложения WCF, например веб-службы ASP.NET, и имитировать их поведение. В следующих разделах сравниваются веб-службы ASP.NET и WCF в зависимости от того, что требуется для разработки приложений с использованием обеих технологий.

## <a name="data-representation"></a>Представление данных

Разработка веб-службы с помощью ASP.NET обычно начинается с определения сложных типов данных, которые будет использовать служба. ASP.NET предполагает использование сериализатора <xref:System.Xml.Serialization.XmlSerializer> для преобразования представленных типами .NET Framework данных в XML для передачи службе или от службы и для преобразования полученных в виде XML данных в объекты .NET Framework. Определение сложных типов данных, которые будет использовать служба ASP.NET, требует определения классов .NET Framework, которые <xref:System.Xml.Serialization.XmlSerializer> может сериализовать в XML и из XML. Такие классы могут быть написаны вручную или сформированы из определений типов в схеме XML с помощью утилиты командной строки для поддержки схем XML/типов данных (xsd.exe).

Ниже перечислены основные моменты, которые необходимо знать для определения классов .NET Framework, которые <xref:System.Xml.Serialization.XmlSerializer> сможет сериализовать в XML и из XML.

- В XML преобразуются только открытые поля и свойства объектов .NET Framework.

- Экземпляры классов коллекций могут быть сериализованы в XML только при условии реализации классами интерфейса <xref:System.Collections.IEnumerable> или <xref:System.Collections.ICollection>.

- Классы, реализующие интерфейс <xref:System.Collections.IDictionary>, такие как <xref:System.Collections.Hashtable>, не могут быть сериализованы в XML.

- Пространство имен <xref:System.Xml.Serialization> содержит огромное множество типов атрибутов, которые можно добавлять в классы .NET Framework и их члены для управления тем, как экземпляры класса будут представлены в XML.

Разработка приложений WCF обычно начинается с определения сложных типов. WCF может быть создана для использования тех же типов .NET Framework, что и веб-службы ASP.NET.

WCF<xref:System.Runtime.Serialization.DataContractAttribute> и<xref:System.Runtime.Serialization.DataMemberAttribute> может быть добавлена к типам .NET Framework, чтобы указать, что экземпляры типа должны быть сериализованы в XML, а какие конкретные поля или свойства типа должны быть сериализованы, как показано в следующем образце кода.

```csharp
//Example One:
[DataContract]
public class LineItem
{
    [DataMember]
    public string ItemNumber;
    [DataMember]
    public decimal Quantity;
    [DataMember]
    public decimal UnitPrice;
}

//Example Two:
public class LineItem
{
    [DataMember]
    private string itemNumber;
    [DataMember]
    private decimal quantity;
    [DataMember]
    private decimal unitPrice;

    public string ItemNumber
    {
      get
      {
          return this.itemNumber;
      }

      set
      {
          this.itemNumber = value;
      }
    }

    public decimal Quantity
    {
        get
        {
            return this.quantity;
        }

        set
        {
            this.quantity = value;
        }
    }

    public decimal UnitPrice
    {
      get
      {
          return this.unitPrice;
      }

      set
      {
          this.unitPrice = value;
      }
    }
}

//Example Three:
public class LineItem
{
     private string itemNumber;
     private decimal quantity;
     private decimal unitPrice;

     [DataMember]
     public string ItemNumber
     {
       get
       {
          return this.itemNumber;
       }

       set
       {
           this.itemNumber = value;
       }
     }

     [DataMember]
     public decimal Quantity
     {
          get
          {
              return this.quantity;
          }

          set
          {
             this.quantity = value;
          }
     }

     [DataMember]
     public decimal UnitPrice
     {
          get
          {
              return this.unitPrice;
          }

          set
          {
              this.unitPrice = value;
          }
     }
}
```

Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> означает, что ноль или более полей или свойств типа должны быть сериализованы, тогда как атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> указывает, что определенное поле или свойство должно быть сериализовано. Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> может быть применен к классу или структуре. Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> может быть применен к полю или свойству, причем поля и свойства, к которым применяется атрибут, могут быть как открытыми, так и закрытыми. Экземпляры типов, к которым применен <xref:System.Runtime.Serialization.DataContractAttribute> объект, называются контрактами данных в WCF. Они сериализуются в XML с помощью сериализатора <xref:System.Runtime.Serialization.DataContractSerializer>.

Ниже перечислены важные различия между использованием сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> и использованием сериализатора <xref:System.Xml.Serialization.XmlSerializer> и различных атрибутов из пространства имен <xref:System.Xml.Serialization>.

- Сериализатор <xref:System.Xml.Serialization.XmlSerializer> и атрибуты из пространства имен <xref:System.Xml.Serialization> предназначены для того, чтобы разработчик мог сопоставлять типы .NET Framework с любым допустимым типом, определенным в схеме XML, и как таковые позволяют очень точно управлять тем, как тип будет представлен в XML. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> и атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> позволяют контролировать представление типа в XML в очень небольшой степени. Можно указать только пространства имен и имена, используемые для представления типа и его полей или свойств в XML, а также последовательности, в которой поля и свойства будут идти в XML.

  ```csharp
  [DataContract(
  Namespace="urn:Contoso:2006:January:29",
  Name="LineItem")]
  public class LineItem
  {
        [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]
        public string itemNumber;
        [DataMember(Name="Quantity",IsRequired=false,Order = 1)]
        public decimal quantity;
        [DataMember(Name="Price",IsRequired=false,Order = 2)]
        public decimal unitPrice;
  }
  ```

  Все остальные аспекты структуры XML-данных, используемых для представления типа .NET, определяет <xref:System.Runtime.Serialization.DataContractSerializer>.

- Благодаря ограниченности контроля разработчика над представлением типа в XML процесс сериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer> весьма предсказуем и, следовательно, его легче оптимизировать. Практическое преимущество такого принципа работы <xref:System.Runtime.Serialization.DataContractSerializer> состоит в повышении производительности примерно на десять процентов.

- Атрибуты, предназначенные для использования в сочетании с сериализатором <xref:System.Xml.Serialization.XmlSerializer>, не указывают, какие поля или свойства сериализуются в XML, тогда как атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, предназначенный для использования в сочетании с сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, явно показывает, какие поля или свойства сериализуются. Следовательно, контракты данных представляют собой явные контракты о структуре данных, которые будет отправлять и получать приложение.

- Сериализатор <xref:System.Xml.Serialization.XmlSerializer> может преобразовывать в XML только открытые члены объекта .NET; сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> может преобразовывать в XML члены объектов независимо от модификаторов доступа этих членов.

- Вследствие способности сериализовать в XML закрытые члены типов для сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> характерно меньшее количество ограничений на типы .NET, которые он может сериализовать в XML. В частности, он способен преобразовывать в XML такие типы, как <xref:System.Collections.Hashtable>, который реализует интерфейс <xref:System.Collections.IDictionary>. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> со значительно большей вероятностью сможет сериализовать в XML экземпляры любого уже существующего типа .NET без внесения в тип изменений или разработки для него оболочки.

- Другим следствием способности сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> получать доступ к закрытым членам типа является то, что ему требуется полное доверие, тогда как сериализатор <xref:System.Xml.Serialization.XmlSerializer> этого не требует. Разрешение на доступ к коду полного доверия обеспечивает полный доступ ко всем ресурсам на компьютере, к которым можно получить доступ с помощью учетных данных, с которыми выполняется код. Этот параметр следует использовать с осторожностью, так как полностью доверенный код получает доступ ко всем ресурсам на компьютере.

- Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> предусматривает некоторую поддержку управления версиями.

  - Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> имеет свойство <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>, которому можно присваивать значение false для добавляемых в новые версии (т. е. отсутствовавших в предыдущих версиях) контракта данных членов, что позволяет приложениям с более новой версией контракта обрабатывать более ранние версии типа.

  - Реализуя в контракте данных интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>, разработчик может позволить сериализатору <xref:System.Runtime.Serialization.DataContractSerializer> передавать члены, определенные в более новых версиях контракта данных, через приложения с более ранними версиями контракта.

Несмотря на все различия, XML-данные, в которые <xref:System.Xml.Serialization.XmlSerializer> сериализует тип, по умолчанию семантически идентичны XML-данным, в которые сериализует тип <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML определено явным образом. Следующий класс, имеющий атрибуты для использования с обоими сериализаторами, преобразуется в семантически идентичный XML с <xref:System.Xml.Serialization.XmlSerializer> помощью и: <xref:System.Runtime.Serialization.DataContractAttribute>

```csharp
[Serializable]
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]
[DataContract(Namespace="urn:Contoso:2006:January:29")]
public class LineItem
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}
```

Пакет средств разработки программного обеспечения (SDK) для Windows включает программу командной строки, которая называется [служебной программой для метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Как и средство XSD. exe, используемое с веб-службами ASP.NET, программа Svcutil. exe может создавать определения типов данных .NET из схемы XML. Типы являются контрактами данных, если сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> способен выдать XML-данные в формате, определенном схемой XML; в противном случае они предназначены для сериализации с помощью <xref:System.Xml.Serialization.XmlSerializer>. Svcutil. exe также может создавать XML-схемы на основе контрактов данных с помощью `dataContractOnly` переключателя.

> [!NOTE]
> Несмотря на то <xref:System.Xml.Serialization.XmlSerializer>, что ASP.NET веб-службы используют, и режим совместимости WCF ASP.NET делает службы WCF <xref:System.Xml.Serialization.XmlSerializer>более сходными с поведением веб-служб ASP.NET, параметр совместимости ASP.NET не ограничивает один для использования. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> можно использовать и для служб, выполняемых в режиме совместимости с ASP.NET.

## <a name="service-development"></a>Разработка служб

Для разработки службы с использованием ASP.NET обычно требовалось добавлять атрибут <xref:System.Web.Services.WebService> в класс и атрибут <xref:System.Web.Services.WebMethodAttribute> во все методы этого класса, которые являются операциями службы:

```csharp
[WebService]
public class Service : T:System.Web.Services.WebService
{
    [WebMethod]
    public string Echo(string input)
    {
       return input;
    }
}
```

В ASP.NET 2.0 появилась возможность добавления атрибутов <xref:System.Web.Services.WebService> и <xref:System.Web.Services.WebMethodAttribute> в интерфейс, а не в класс, и написания класса для реализации этого интерфейса:

```csharp
[WebService]
public interface IEcho
{
    [WebMethod]
    string Echo(string input);
}

public class Service : IEcho
{

   public string Echo(string input)
   {
        return input;
    }
}
```

Этот вариант является предпочтительным, так как интерфейс с атрибутом <xref:System.Web.Services.WebService> составляет контракт для операций, выполняемых службой, доступный для повторного использования в различных классах, которые могут реализовывать этот же контракт другими способами.

Служба WCF предоставляется путем определения одной или нескольких конечных точек WCF. Конечная точка определяется адресом, привязкой и контрактом службы. Адрес определяет местонахождение службы. Привязка задает способ обмена данными со службой. Контракт службы определяет операции, которые может выполнять служба.

Контракт службы обычно определяется в первую очередь, путем добавления атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> в интерфейс:

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

Указывает, что интерфейс определяет контракт службы WCF, а также <xref:System.ServiceModel.OperationContractAttribute> указывает, какие из методов интерфейса определяют операции контракта службы. <xref:System.ServiceModel.ServiceContractAttribute>

После определения контракта службы он реализуется в классе - путем реализации в классе интерфейса, которым определяется контракт службы:

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

Класс, реализующий контракт службы, называется типом службы в WCF.

Следующий шаг - связать адрес и привязку с типом службы. Это обычно делается в файле конфигурации путем непосредственного редактирования файла или с помощью редактора конфигурации, предоставленного в WCF. Ниже приведен пример файла конфигурации.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
     <system.serviceModel>
      <services>
      <service name="Service ">
       <endpoint
        address="EchoService"
        binding="basicHttpBinding"
        contract="IEchoService "/>
      </service>
      </services>
     </system.serviceModel>
</configuration>
```

Привязка задает набор протоколов для обмена данными с приложением. В следующей таблице перечислены предоставляемые системой привязки, соответствующие стандартным вариантам.

|name|Цель|
|----------|-------------|
|BasicHttpBinding|Взаимодействие с веб-службами и клиентами, поддерживающими спецификации WS-BasicProfile 1.1 и Basic Security Profile 1.0.|
|WSHttpBinding|Взаимодействие с веб-службами и клиентами, поддерживающими протоколы WS-* через HTTP.|
|WSDualHttpBinding|Дуплексная связь по протоколу HTTP, при которой получатель первоначального сообщения не отвечает непосредственно первоначальному отправителю, но может передавать любое количество ответов в течение некоторого периода времени, используя HTTP в соответствии с протоколами WS-*.|
|WSFederationBinding|Связь по протоколу HTTP, при которой доступом к ресурсам службы можно управлять на основе учетных данных, выданных явно идентифицированным поставщиком учетных данных.|
|NetTcpBinding|Безопасная, надежная и высокопроизводительная связь между программными сущностями WCF по сети.|
|NetNamedPipeBinding|Безопасная, надежная и высокопроизводительная связь между сущностями программного обеспечения WCF на одном компьютере.|
|NetMsmqBinding|Взаимодействие между сущностями программного обеспечения WCF с помощью MSMQ.|
|MsmqIntegrationBinding|Обмен данными между программной сущностью WCF и другой сущностью программы с помощью MSMQ.|
|NetPeerTcpBinding|Взаимодействие между сущностями программного обеспечения WCF с помощью одноранговых сетей Windows.|

Предоставляемая системой привязка <xref:System.ServiceModel.BasicHttpBinding> включает набор протоколов, поддерживаемых веб-службами ASP.NET.

Пользовательские привязки для приложений WCF легко определяются как коллекции классов элементов привязки, которые WCF использует для реализации отдельных протоколов. Можно писать новые элементы привязки для представления дополнительных протоколов.

Внутреннее поведение типов служб можно корректировать, используя свойства семейства классов, называемых поведениями. В следующем примере с помощью класса <xref:System.ServiceModel.ServiceBehaviorAttribute> указывается, что тип службы должен быть многопоточным.

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

Некоторые поведения, такие как <xref:System.ServiceModel.ServiceBehaviorAttribute>, представляют собой атрибуты. Другие, имеющие свойства, которые может потребоваться задавать администраторам, могут быть изменены в конфигурации приложения.

При программировании типов служб часто используется класс <xref:System.ServiceModel.OperationContext>. Его статическое свойство <xref:System.ServiceModel.OperationContext.Current%2A> обеспечивает доступ к информации о контексте, в котором выполняется операция. <xref:System.ServiceModel.OperationContext> аналогичен классам <xref:System.Web.HttpContext> и <xref:System.EnterpriseServices.ContextUtil>.

## <a name="hosting"></a>Размещение

Веб-службы ASP.NET компилируются в сборку библиотеки классов. Формируется файл, называемый файлом службы, который имеет расширение ASMX и содержит директиву `@ WebService`. Эта директива идентифицирует класс, содержащий код для службы и сборку, в которой он находится.

`<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>`

Файл службы копируется в корень приложения ASP.NET в службах IIS, а сборка копируется в подкаталог \bin этого корня приложения. После этого приложение будет доступно по URL-адресу файла службы в корне приложения.

Службы WCF могут быть размещены в IIS 5,1 или 6,0, службе активации Windows (WAS), входящей в состав IIS 7,0, и в любом приложении .NET. Чтобы службу можно было разместить в IIS 5.1 или 6.0, в качестве транспортного протокола связи она должна использовать HTTP.

Чтобы разместить службу в IIS 5.1, 6.0 или в WAS, выполните следующие действия.

1. Скомпилируйте тип службы в сборку библиотеки классов.

2. Создайте файл службы с расширением SVC с директивой `@ ServiceHost` для идентификации типа службы:

    `<%@ServiceHost language="c#" Service="MyService" %>`

3. Скопируйте файл службы в виртуальный каталог, а сборку в подкаталог \bin этого виртуального каталога.

4. Скопируйте файл конфигурации в виртуальный каталог и назовите его Web.config.

После этого приложение будет доступно по URL-адресу файла службы в корне приложения.

Чтобы разместить службу WCF в приложении .NET, Скомпилируйте тип службы в сборку библиотеки классов, на которую ссылается приложение, и запрограммировать приложение для размещения службы с помощью <xref:System.ServiceModel.ServiceHost> класса. Ниже приведен простой пример требуемого программирования:

```csharp
string httpBaseAddress = "http://www.contoso.com:8000/";
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";

Uri httpBaseAddressUri = new Uri(httpBaseAddress);
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);

Uri[] baseAddresses = new Uri[] {
 httpBaseAddressUri,
 tcpBaseAddressUri};

using(ServiceHost host = new ServiceHost(
typeof(Service), //"Service" is the name of the service type baseAddresses))
{
     host.Open();

     […] //Wait to receive messages
     host.Close();
}
```

В этом примере показано задание адресов для одного или нескольких транспортных протоколов при построении объекта <xref:System.ServiceModel.ServiceHost>. Эти адреса называются базовыми адресами.

Адрес, предоставленный для любой конечной точки службы WCF, является адресом относительно базового адреса узла конечной точки. Узел размещения может иметь по одному базовому адресу для каждого транспортного протокола связи. В приведенном выше примере файла конфигурации выбранная для конечной точки привязка <xref:System.ServiceModel.BasicHttpBinding> предполагает использование в качестве транспорта протокола HTTP, поэтому адрес конечной точки — `EchoService`— рассматривается относительно базового HTTP-адреса узла. В случае размещения в предыдущем примере основным адресом HTTP является `http://www.contoso.com:8000/`. Для службы, размещенной в IIS или WAS, базовый адрес - это URL-адрес файла службы для этой службы.

Для использования параметра режима совместимости WCF ASP.NET можно использовать только службы, размещенные в IIS или WAS, которые настроены с протоколом HTTP в качестве транспортного протокола. Для включения этого режима необходимо выполнить следующие шаги.

1. Программист должен добавить атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> в тип службы и указать, что режим совместимости с ASP.NET допускается либо требуется.

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. Администратор должен настроить приложение на использование режима совместимости с ASP.NET.

    ```xml
    <configuration>
         <system.serviceModel>
          <services>
          […]
          </services>
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
        </system.serviceModel>
    </configuration>
    ```

    Приложения WCF также можно настроить на использование ASMX в качестве расширения для файлов служб, а не SVC.

    ```xml
    <system.web>
         <compilation>
          <compilation debug="true">
          <buildProviders>
           <remove extension=".asmx"/>
           <add extension=".asmx"
            type="System.ServiceModel.ServiceBuildProvider,
            System.ServiceModel,
            Version=3.0.0.0,
            Culture=neutral,
            PublicKeyToken=b77a5c561934e089" />
          </buildProviders>
          </compilation>
         </compilation>
    </system.web>
    ```

    Этот параметр позволяет сохранить необходимость изменения клиентов, настроенных на использование URL-адресов файлов службы ASMX при изменении службы для использования WCF.

## <a name="client-development"></a>Разработка клиентов

Клиенты для веб-служб ASP.NET формируются с помощью программы командной строки WSDL.exe, которая предоставляет URL-адрес ASMX-файла в качестве входных данных. Соответствующий инструмент, предоставляемый WCF, является [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Он создает модуль кода с определением контракта службы и определением клиентского класса WCF. Кроме того, она формирует файл конфигурации с адресом и привязкой службы.

При программировании клиента удаленной службы обычно рекомендуется программировать в соответствии с асинхронной моделью. Код, формируемый программой WSDL.exe, по умолчанию всегда предусматривает и синхронную, и асинхронную модели. Код, формируемый [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , может предоставлять любой шаблон. По умолчанию предусматривается синхронная модель. При выполнении программы с переключателем `/async` сформированный код предусматривает асинхронную модель.

Нет никакой гарантии, что имена в клиентских классах WCF, созданных ASP. Программа NET. exe по умолчанию соответствует именам в клиентских классах WCF, созданных средством Svcutil. exe. В частности, имена свойств классов, которые должны сериализоваться с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>, в формируемом программой Svcutil.exe коде по умолчанию получают суффикс "Property", который отсутствует в коде, формируемом WSDL.exe.

## <a name="message-representation"></a>Представление сообщений

Заголовки сообщений SOAP, отправляемых и получаемых веб-службами ASP.NET, можно настроить. Из класса <xref:System.Web.Services.Protocols.SoapHeader> наследуется класс для определения структуры заголовка, после чего применяется атрибут <xref:System.Web.Services.Protocols.SoapHeaderAttribute>, чтобы указать на присутствие заголовка.

```csharp
public class SomeProtocol : SoapHeader
{
     public long CurrentValue;
     public long Total;
}

[WebService]
public interface IEcho
{
     SomeProtocol ProtocolHeader
     {
      get;
     set;
     }

     [WebMethod]
     [SoapHeader("ProtocolHeader")]
     string PlaceOrders(PurchaseOrderType order);
}

public class Service: WebService, IEcho
{
     private SomeProtocol protocolHeader;

     public SomeProtocol ProtocolHeader
     {
         get
         {
              return this.protocolHeader;
         }

         set
         {
              this.protocolHeader = value;
         }
     }

     string PlaceOrders(PurchaseOrderType order)
     {
         long currentValue = this.protocolHeader.CurrentValue;
     }
}
```

WCF предоставляет атрибуты,, и <xref:System.ServiceModel.MessageContractAttribute> <xref:System.ServiceModel.MessageBodyMemberAttribute> для <xref:System.ServiceModel.MessageHeaderAttribute>описания структуры сообщений SOAP, отправленных и полученных службой.

```csharp
[DataContract]
public class SomeProtocol
{
     [DataMember]
     public long CurrentValue;
     [DataMember]
     public long Total;
}

[DataContract]
public class Item
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}

[MessageContract]
public class ItemMessage
{
     [MessageHeader]
     public SomeProtocol ProtocolHeader;
     [MessageBody]
     public Item Content;
}

[ServiceContract]
public interface IItemService
{
     [OperationContract]
     public void DeliverItem(ItemMessage itemMessage);
}
```

Этот синтаксис дает явное представление структуры сообщений, тогда как в веб-службе ASP.NET структура сообщений подразумевается в коде. Кроме того, в синтаксисе ASP.NET заголовки сообщений представлены в виде свойств службы, например `ProtocolHeader` свойства в предыдущем примере, а в синтаксисе WCF они более точно представлены в виде свойств сообщений. Кроме того, WCF позволяет добавлять заголовки сообщений в конфигурацию конечных точек.

```xml
<service name="Service ">
     <endpoint
      address="EchoService"
      binding="basicHttpBinding"
      contract="IEchoService ">
      <headers>
      <dsig:X509Certificate
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
       ...
      </dsig:X509Certificate>
      </headers>
     </endpoint>
</service>
```

Это позволяет обойтись без ссылок на заголовки инфраструктурных протоколов в коде клиента или службы: заголовки добавляются в сообщения в соответствии с тем, как настроена конечная точка.

## <a name="service-description"></a>Описание службы

При выдаче запроса HTTP-GET на ASMX-файл веб-службы ASP.NET с запросом "WSDL" ASP.NET формирует WSDL-код для описания службы. Этот WSDL-код возвращается в качестве ответа на запрос HTTP-GET.

В ASP.NET 2.0 появилась возможность проверять, совместима ли служба со спецификацией Basic Profile 1.1 Организации по обеспечению взаимодействия веб-служб (Web Services-Interoperability Organization, WS-I), и вставлять утверждение о совместимости службы в WSDL. Это делается с помощью параметров `ConformsTo` и `EmitConformanceClaims` атрибута <xref:System.Web.Services.WebServiceBindingAttribute>.

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

WSDL-код, формируемый ASP.NET для службы, можно настраивать. Настройка производится путем создания класса, производного от <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, для добавления элементов в WSDL-код.

Выдача HTTP-запроса GET с запросом WSDL для SVC-файла службы WCF с конечной точкой HTTP, размещенной в IIS 51, 6,0 или WAS, приводит к тому, что WCF отвечает на WSDL для описания службы. Передача запроса HTTP-GET с запросом «WSDL» на базовый HTTP-адрес службы, размещенной в приложении .NET, имеет тот же эффект, если параметр httpGetEnabled имеет значение true.

Однако WCF также реагирует на запросы WS-MetadataExchange с WSDL, который создается для описания службы. Веб-службы ASP.NET не располагают встроенной поддержкой запросов WS-MetadataExchange.

WSDL-код, создаваемый WCF, можно настроить с большой нагрузкой. Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> предоставляет некоторые средства для настройки WSDL-кода. Кроме того, WCF можно настроить так, чтобы она не создавала WSDL, а использовала статический WSDL-файл по указанному URL.

```xml
<behaviors>
     <behavior name="DescriptionBehavior">
     <metadataPublishing
      enableMetadataExchange="true"
      enableGetWsdl="true"
      enableHelpPage="true"
      metadataLocation=
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>
     </behavior>
</behaviors>
```

## <a name="exception-handling"></a>Обработка исключений

В веб-службах ASP.NET необработанные исключения возвращаются клиентам в виде ошибок SOAP. Также можно явно вызывать исключения класса <xref:System.Web.Services.Protocols.SoapException>, что позволяет в большей степени контролировать содержимое ошибки SOAP, передаваемое клиенту.

В службах WCF необработанные исключения не возвращаются клиентам в виде ошибок SOAP, чтобы предотвратить непреднамеренное предоставление конфиденциальной информации через исключения. Предусмотрен параметр конфигурации для возвращения необработанных исключений клиентам в целях отладки.

Для возвращения ошибок SOAP клиентам можно вызывать исключения универсального типа - <xref:System.ServiceModel.FaultException%601> - используя в качестве универсального типа тип контракта данных. Также можно добавлять в операции атрибуты <xref:System.ServiceModel.FaultContractAttribute> для указания того, какие ошибки могут быть выданы операцией.

```csharp
[DataContract]
public class MathFault
{
     [DataMember]
     public string operation;
     [DataMember]
     public string problemType;
}

[ServiceContract]
public interface ICalculator
{
     [OperationContract]
     [FaultContract(typeof(MathFault))]
     int Divide(int n1, int n2);
}
```

В этом случае возможные ошибки объявляются в WSDL-коде для службы, что дает разработчикам клиентов возможность предвидеть, какие ошибки могут произойти в результате операции, и написать соответствующие инструкции catch.

```csharp
try
{
     result = client.Divide(value1, value2);
}
catch (FaultException<MathFault> e)
{
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "
  + e.Detail.operation
  + ". Problem: "
  + e.Detail.problemType);
}
```

## <a name="state-management"></a>Управление состоянием

Класс, используемый для реализации веб-службы ASP.NET, может наследоваться от класса <xref:System.Web.Services.WebService>.

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

В этом случае класс можно запрограммировать на использование свойства Context базового класса <xref:System.Web.Services.WebService> для доступа к объекту <xref:System.Web.HttpContext>. Объект <xref:System.Web.HttpContext> можно использовать для обновления и извлечения информации о состоянии приложения (с помощью его свойства Application) и для обновления и извлечения информации о состоянии сеанса (с помощью его свойства Session).

ASP.NET позволяет в значительной степени контролировать место фактического хранения информации о состоянии сеанса, для доступа к которой используется свойство Session объекта <xref:System.Web.HttpContext>. Эта информация может храниться в файлах cookie, в базе данных, в памяти текущего сервера или в памяти указанного сервера. Место хранения информации указывается в файле конфигурации службы.

WCF предоставляет расширяемые объекты для управления состоянием. Расширяемые объекты - это объекты, реализующие интерфейс <xref:System.ServiceModel.IExtensibleObject%601>. Наиболее важными из расширяемых объектов являются <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.InstanceContext>. `ServiceHostBase` позволяет сохранять состояние, к которому могут обращаться все экземпляры всех типов служб на одном и том же узле, тогда как `InstanceContext` позволяет сохранять состояние, к которому может обращаться любой код, выполняемый в одном экземпляре типа службы.

Здесь тип `TradingSystem`службы,, имеет объект <xref:System.ServiceModel.ServiceBehaviorAttribute> , который указывает, что все вызовы из одного и того же экземпляра клиента WCF направляются на один и тот же экземпляр типа службы.

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

Класс, `DealData`, определяет состояние, к которому может обращаться любой код, выполняемый в одном и том же экземпляре типа службы.

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

В коде типа службы, реализующем одну из операций контракта службы, к состоянию текущего экземпляра типа службы добавляется объект состояния `DealData`.

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

Этот объект состояния затем может быть извлечен и изменен кодом, реализующим другую операцию контракта службы.

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

В то время как ASP.net предоставляет контроль над тем, где <xref:System.Web.HttpContext> на самом деле хранится информация о состоянии в классе, WCF, по крайней мере, в начальной версии, не предоставляет контроль над тем, где хранятся расширяемые объекты. Это является наиболее оптимальной причиной выбора режима совместимости ASP.NET для службы WCF. Если настраиваемое управление состоянием является обязательным условием, выбор режима совместимости с ASP.NET позволяет использовать средства класса <xref:System.Web.HttpContext> в точности так, как они используются в ASP.NET, а также настраивать место хранения информации о состоянии с помощью класса <xref:System.Web.HttpContext>.

## <a name="security"></a>Безопасность

Для защиты веб-служб ASP.NET используются те же механизмы, что и для защиты любого приложения IIS. Так как приложения WCF могут размещаться не только в службах IIS, но и в любом исполняемом файле .NET, варианты защиты приложений WCF должны быть сделаны независимыми от средств IIS. Однако средства, предоставляемые для веб-служб ASP.NET, также доступны для служб WCF, работающих в режиме совместимости ASP.NET.

### <a name="security-authentication"></a>Безопасность: Проверка подлинности

Службы IIS предоставляют средства для управления доступом к приложениям, с помощью которых можно выбрать анонимный доступ или различные режимы проверки подлинности. Аутентификация Windows, дайджест-аутентификация, обычная проверка подлинности и проверка подлинности .NET Passport. Вариант с проверкой подлинности Windows можно использовать для управления доступом к веб-службам ASP.NET. Однако, когда приложения WCF размещаются в службах IIS, службы IIS должны разрешать анонимный доступ к приложению, чтобы проверка подлинности могла управляться самой WCF, что поддерживает проверку подлинности Windows между различными параметрами. Другие встроенные средства включают маркеры имени пользователя, сертификаты X.509, маркеры SAML и карту CardSpace; также можно определять пользовательские механизмы проверки подлинности.

### <a name="security-impersonation"></a>Безопасность: Олицетворение

ASP.NET предоставляет элемент удостоверения, посредством которого веб-служба ASP.NET может олицетворять определенного пользователя или любого пользователя, учетные данные которого переданы в текущем запросе. Этот элемент можно использовать для настройки олицетворения в приложениях WCF, работающих в режиме совместимости ASP.NET.

Система конфигурации WCF предоставляет свой собственный элемент Identity для обозначения конкретного пользователя для олицетворения. Кроме того, клиенты и службы WCF могут быть настроены независимо для олицетворения. Клиенты можно настроить на олицетворение текущего пользователя при передаче запросов.

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

Операции службы можно настроить на олицетворение любого пользователя, учетные данные которого переданы в текущем запросе.

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a>Безопасность: Авторизация с помощью списков управления доступом

Для ограничения доступа к ASMX-файлам можно использовать списки управления доступом (ACL). Однако списки ACL для файлов WCF. svc игнорируются, за исключением режима совместимости ASP.NET.

### <a name="security-role-based-authorization"></a>Безопасность: Авторизация на основе ролей

Режим проверки подлинности Windows, предоставляемый службами IIS, можно использовать в сочетании с предусмотренным в языке конфигурации ASP.NET элементом авторизации для упрощения авторизации на основе ролей для веб-служб ASP.NET, основанных на группах Windows, которым назначены пользователи. В ASP.NET 2.0 появился более общий механизм авторизации на основе ролей: поставщики ролей.

Поставщики ролей - это классы, реализующие базовый интерфейс для отправки запросов о ролях, которым назначен пользователь, причем каждый поставщик ролей предназначен для извлечения этой информации из определенного источника. ASP.NET 2.0 предоставляет поставщик ролей, который может извлекать назначения ролей из базы данных Microsoft SQL Server, и еще один поставщик, способный извлекать назначения ролей из диспетчера авторизации Windows Server 2003.

Механизм поставщика ролей можно фактически использовать независимо от ASP.NET в любом приложении .NET, включая приложение WCF. В следующем примере конфигурации для приложения WCF показано, как использование поставщика ролей ASP.NET является параметром, выбранным с <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>помощью.

```xml
<system.serviceModel>
     <services>
         <service name="Service.ResourceAccessServiceType"
             behaviorConfiguration="ServiceBehavior">
             <endpoint
              address="ResourceAccessService"
              binding="wsHttpBinding"
              contract="Service.IResourceAccessContract"/>
         </service>
     </services>
     <behaviors>
       <behavior name="ServiceBehavior">
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
      </behavior>
     </behaviors>
</system.serviceModel>
```

### <a name="security-claims-based-authorization"></a>Безопасность: Авторизация на основе утверждений

Одним из наиболее важных нововведений WCF является тщательная Поддержка авторизации доступа к защищенным ресурсам на основе заявок. Утверждения состоят из типа, права и значения. В качестве примера можно привести водительское удостоверение: оно содержит ряд утверждений о своем предъявителе, одним из которых является дата рождения предъявителя. Тип этого утверждения - дата рождения, а значение утверждения - дата рождения водителя. Право, которое утверждение дает предъявителю, указывает, что предъявитель может делать со значением утверждения. В случае утверждения даты рождения водителя право состоит во владении: эта дата рождения принадлежит водителю, однако он не может, например, изменять ее. Авторизация на основе утверждений включает в себя авторизацию на основе ролей, поскольку роли являются одним из типов утверждений.

Авторизация на основе утверждений осуществляется путем сравнения набора утверждений с требованиями доступа к операции и предоставления доступа к операции или отказа в доступе к операции в зависимости от результатов этого сравнения. В WCF можно указать класс, который будет использоваться для выполнения авторизации на основе утверждений, путем присвоения значения `ServiceAuthorizationManager` <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>свойству.

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

Классы, используемые для выполнения авторизации на основе утверждений, должны быть производными от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, в котором имеется только один метод для переопределения - `AccessCheck()`. WCF вызывает этот метод каждый раз при вызове операции службы и предоставляет <xref:System.ServiceModel.OperationContext> объект, который имеет утверждения для пользователя в его `ServiceSecurityContext.AuthorizationContext` свойстве. WCF выполняет сборку утверждений о пользователе из любого маркера безопасности, предоставленного пользователем для проверки подлинности, что оставляет за собой задачу оценки того, достаточно ли этих утверждений для рассматриваемой операции.

WCF автоматически собирает утверждения из любого вида маркера безопасности, так как делает код для авторизации на основе утверждений полностью независимым от механизма проверки подлинности. В противоположность этому авторизация с использованием списков ACL или ролей в ASP.NET тесно связана с проверкой подлинности Windows.

### <a name="security-confidentiality"></a>Безопасность: Конфиденциальность

Конфиденциальность сообщений, отправляемых и принимаемых веб-службами ASP.NET, может быть обеспечена на уровне транспорта путем настройки приложения в IIS на использование протокола HTTPS. То же самое можно сделать для приложений WCF, размещенных в IIS. Однако приложения WCF, размещенные за пределами служб IIS, также можно настроить для использования защищенного транспортного протокола. Более важно, что приложения WCF также можно настроить для защиты сообщений перед их передачей с помощью протокола WS-Security. Защита только тела сообщения с использованием WS-Security позволяет передавать его с соблюдением конфиденциальности в пункт назначения через посредников.

## <a name="globalization"></a>Глобализация

Язык конфигурации ASP.NET позволяет задавать язык и региональные параметры для отдельных служб. WCF не поддерживает этот параметр конфигурации, за исключением режима совместимости ASP.NET. Для локализации службы WCF, которая не использует режим совместимости ASP.NET, Скомпилируйте тип службы в сборках, зависящих от языка и региональных параметров, и разместите отдельные конечные точки, зависящие от языка и региональных параметров, для каждой сборки, зависящей от культуры.

## <a name="see-also"></a>См. также

- [Сравнение веб-служб ASP.NET с веб-службами на основе WCF по назначению и используемым стандартам](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
