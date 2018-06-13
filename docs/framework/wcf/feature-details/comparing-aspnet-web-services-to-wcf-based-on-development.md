---
title: Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: fcf2d204d9d59a29024ff09d92be2a7b9339fce9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496654"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a>Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки
Windows Communication Foundation (WCF) имеется параметр режима совместимости ASP.NET позволяет программировать и настраивать как веб-служб ASP.NET в WCF приложения и имитировать их поведение. В следующих разделах сравниваются веб-служб ASP.NET и WCF зависимости от того, что необходимо для разработки приложений с использованием обеих технологий.  
  
## <a name="data-representation"></a>Представление данных  
 Разработка веб-службы с помощью ASP.NET обычно начинается с определения сложных типов данных, которые будет использовать служба. ASP.NET предполагает использование сериализатора <xref:System.Xml.Serialization.XmlSerializer> для преобразования представленных типами .NET Framework данных в XML для передачи службе или от службы и для преобразования полученных в виде XML данных в объекты .NET Framework. Определение сложных типов данных, которые будет использовать служба ASP.NET, требует определения классов .NET Framework, которые <xref:System.Xml.Serialization.XmlSerializer> может сериализовать в XML и из XML. Такие классы могут быть написаны вручную или сформированы из определений типов в схеме XML с помощью утилиты командной строки для поддержки схем XML/типов данных (xsd.exe).  
  
 Ниже перечислены основные моменты, которые необходимо знать для определения классов .NET Framework, которые <xref:System.Xml.Serialization.XmlSerializer> сможет сериализовать в XML и из XML.  
  
-   В XML преобразуются только открытые поля и свойства объектов .NET Framework.  
  
-   Экземпляры классов коллекций могут быть сериализованы в XML только при условии реализации классами интерфейса <xref:System.Collections.IEnumerable> или <xref:System.Collections.ICollection>.  
  
-   Классы, реализующие интерфейс <xref:System.Collections.IDictionary>, такие как <xref:System.Collections.Hashtable>, не могут быть сериализованы в XML.  
  
-   Пространство имен <xref:System.Xml.Serialization> содержит огромное множество типов атрибутов, которые можно добавлять в классы .NET Framework и их члены для управления тем, как экземпляры класса будут представлены в XML.  
  
 Разработка приложений WCF обычно также начинается с определения сложных типов. Чтобы использовать те же типы .NET Framework в качестве веб-службы ASP.NET можно сделать WCF.  
  
 WCF<xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> можно добавить в типы .NET Framework, чтобы указать, что экземпляры типа должны быть сериализованы в XML, а также какие конкретные поля или свойства типа должны быть сериализованы, как показано в следующем образце кода.  
  
```  
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
  
 Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> означает, что ноль или более полей или свойств типа должны быть сериализованы, тогда как атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> указывает, что определенное поле или свойство должно быть сериализовано. Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> может быть применен к классу или структуре. Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> может быть применен к полю или свойству, причем поля и свойства, к которым применяется атрибут, могут быть как открытыми, так и закрытыми. Экземпляры типов, имеющих <xref:System.Runtime.Serialization.DataContractAttribute> применены к их называются контрактами данных WCF. Они сериализуются в XML с помощью сериализатора <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Ниже перечислены важные различия между использованием сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> и использованием сериализатора <xref:System.Xml.Serialization.XmlSerializer> и различных атрибутов из пространства имен <xref:System.Xml.Serialization>.  
  
-   Сериализатор <xref:System.Xml.Serialization.XmlSerializer> и атрибуты из пространства имен <xref:System.Xml.Serialization> предназначены для того, чтобы разработчик мог сопоставлять типы .NET Framework с любым допустимым типом, определенным в схеме XML, и как таковые позволяют очень точно управлять тем, как тип будет представлен в XML. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> и атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> позволяют контролировать представление типа в XML в очень небольшой степени. Можно указать только пространства имен и имена, используемые для представления типа и его полей или свойств в XML, а также последовательности, в которой поля и свойства будут идти в XML.  
  
    ```  
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
  
-   Благодаря ограниченности контроля разработчика над представлением типа в XML процесс сериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer> весьма предсказуем и, следовательно, его легче оптимизировать. Практическое преимущество такого принципа работы <xref:System.Runtime.Serialization.DataContractSerializer> состоит в повышении производительности примерно на десять процентов.  
  
-   Атрибуты, предназначенные для использования в сочетании с сериализатором <xref:System.Xml.Serialization.XmlSerializer>, не указывают, какие поля или свойства сериализуются в XML, тогда как атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, предназначенный для использования в сочетании с сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, явно показывает, какие поля или свойства сериализуются. Следовательно, контракты данных представляют собой явные контракты о структуре данных, которые будет отправлять и получать приложение.  
  
-   Сериализатор <xref:System.Xml.Serialization.XmlSerializer> может преобразовывать в XML только открытые члены объекта .NET; сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> может преобразовывать в XML члены объектов независимо от модификаторов доступа этих членов.  
  
-   Вследствие способности сериализовать в XML закрытые члены типов для сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> характерно меньшее количество ограничений на типы .NET, которые он может сериализовать в XML. В частности, он способен преобразовывать в XML такие типы, как <xref:System.Collections.Hashtable>, который реализует интерфейс <xref:System.Collections.IDictionary>. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> со значительно большей вероятностью сможет сериализовать в XML экземпляры любого уже существующего типа .NET без внесения в тип изменений или разработки для него оболочки.  
  
-   Другим следствием способности сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> получать доступ к закрытым членам типа является то, что ему требуется полное доверие, тогда как сериализатор <xref:System.Xml.Serialization.XmlSerializer> этого не требует. Разрешение доступа кода полное доверие предоставляет полный доступ ко всем ресурсам на компьютере, который может осуществляться с использованием учетных данных, с которыми выполняется код. Этот параметр следует использовать с осторожностью, поскольку полностью доверенный код имеет доступ ко всем ресурсам на компьютере.  
  
-   Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> предусматривает некоторую поддержку управления версиями.  
  
    -   Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> имеет свойство <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>, которому можно присваивать значение false для добавляемых в новые версии (т. е. отсутствовавших в предыдущих версиях) контракта данных членов, что позволяет приложениям с более новой версией контракта обрабатывать более ранние версии типа.  
  
    -   Реализуя в контракте данных интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>, разработчик может позволить сериализатору <xref:System.Runtime.Serialization.DataContractSerializer> передавать члены, определенные в более новых версиях контракта данных, через приложения с более ранними версиями контракта.  
  
 Несмотря на все различия, XML-данные, в которые <xref:System.Xml.Serialization.XmlSerializer> сериализует тип, по умолчанию семантически идентичны XML-данным, в которые сериализует тип <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML определено явным образом. Следующий класс, имеющий атрибуты для использования с обоими сериализаторами, преобразуется в семантически идентичные XML-по <xref:System.Xml.Serialization.XmlSerializer> и <xref:System.Runtime.Serialization.DataContractAttribute>:  
  
```  
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
  
 Пакет средств разработки программного обеспечения Windows (SDK) включает в себя программу командной строки [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Средство xsd.exe, используемое с веб-служб ASP.NET, например Svcutil.exe может создавать определения типов данных .NET из схемы XML. Типы являются контрактами данных, если сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> способен выдать XML-данные в формате, определенном схемой XML; в противном случае они предназначены для сериализации с помощью <xref:System.Xml.Serialization.XmlSerializer>. Svcutil.exe также можно создавать XML-схемы из контрактов данных с помощью его `dataContractOnly` переключения.  
  
> [!NOTE]
>  Несмотря на то, что веб-службы ASP.NET используйте <xref:System.Xml.Serialization.XmlSerializer>и режим совместимости WCF ASP.NET делает служб WCF, которые имитируют поведение веб-службы ASP.NET, ASP.NET, режим совместимости не означает, что с помощью <xref:System.Xml.Serialization.XmlSerializer>. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> можно использовать и для служб, выполняемых в режиме совместимости с ASP.NET.  
  
## <a name="service-development"></a>Разработка служб  
 Для разработки службы с использованием ASP.NET обычно требовалось добавлять атрибут <xref:System.Web.Services.WebService> в класс и атрибут <xref:System.Web.Services.WebMethodAttribute> во все методы этого класса, которые являются операциями службы:  
  
```  
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
  
```  
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
  
 Служба WCF предоставляется путем определения одного или нескольких конечных точек WCF. Конечная точка определяется адресом, привязкой и контрактом службы. Адрес определяет местонахождение службы. Привязка задает способ обмена данными со службой. Контракт службы определяет операции, которые может выполнять служба.  
  
 Контракт службы обычно определяется в первую очередь, путем добавления атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> в интерфейс:  
  
```  
[ServiceContract]  
public interface IEcho  
{  
     [OperationContract]  
     string Echo(string input);  
}  
```  
  
 <xref:System.ServiceModel.ServiceContractAttribute> Указывает, что интерфейс определяет контракт службы WCF и <xref:System.ServiceModel.OperationContractAttribute> указывает, если таковые имеются, методов интерфейса определяют операции контракта службы.  
  
 После определения контракта службы он реализуется в классе - путем реализации в классе интерфейса, которым определяется контракт службы:  
  
```  
public class Service : IEcho  
{  
    public string Echo(string input)  
    {  
       return input;  
    }  
}  
```  
  
 Класс, реализующий контракт службы упоминается как служба, введите в WCF.  
  
 Следующий шаг - связать адрес и привязку с типом службы. Это обычно делается в файле конфигурации, либо путем редактирования файла напрямую или с помощью редактора конфигурации, в состав WCF. Ниже приведен пример файла конфигурации.  
  
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
  
|Имя|Назначение|  
|----------|-------------|  
|BasicHttpBinding|Взаимодействие с веб-службами и клиентами, поддерживающими спецификации WS-BasicProfile 1.1 и Basic Security Profile 1.0.|  
|WSHttpBinding|Взаимодействие с веб-службами и клиентами, поддерживающими протоколы WS-* через HTTP.|  
|WSDualHttpBinding|Дуплексная связь по протоколу HTTP, при которой получатель первоначального сообщения не отвечает непосредственно первоначальному отправителю, но может передавать любое количество ответов в течение некоторого периода времени, используя HTTP в соответствии с протоколами WS-*.|  
|WSFederationBinding|Связь по протоколу HTTP, при которой доступом к ресурсам службы можно управлять на основе учетных данных, выданных явно идентифицированным поставщиком учетных данных.|  
|NetTcpBinding|Безопасная, надежная и высокой производительности обмена данными между программными сущностями WCF по сети.|  
|NetNamedPipeBinding|Безопасная, надежная и высокой производительности обмена данными между программными сущностями WCF на том же компьютере.|  
|NetMsmqBinding|Обмен данными между программными сущностями WCF с помощью MSMQ.|  
|MsmqIntegrationBinding|Взаимодействие между WCF программного обеспечения и другой сущностью программного обеспечения с помощью MSMQ.|  
|NetPeerTcpBinding|Обмен данными между программными сущностями WCF с помощью Windows-одноранговые сети.|  
  
 Предоставляемая системой привязка <xref:System.ServiceModel.BasicHttpBinding> включает набор протоколов, поддерживаемых веб-службами ASP.NET.  
  
 Пользовательские привязки для приложений WCF легко определять как коллекции классов элементов привязки, используемые в WCF для реализации отдельных протоколов. Можно писать новые элементы привязки для представления дополнительных протоколов.  
  
 Внутреннее поведение типов служб можно корректировать, используя свойства семейства классов, называемых поведениями. В следующем примере с помощью класса <xref:System.ServiceModel.ServiceBehaviorAttribute> указывается, что тип службы должен быть многопоточным.  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]  
public class DerivativesCalculatorServiceType: IDerivativesCalculator  
```  
  
 Некоторые поведения, такие как <xref:System.ServiceModel.ServiceBehaviorAttribute>, представляют собой атрибуты. Другие, имеющие свойства, которые может потребоваться задавать администраторам, могут быть изменены в конфигурации приложения.  
  
 При программировании типов служб часто используется класс <xref:System.ServiceModel.OperationContext>. Его статическое свойство <xref:System.ServiceModel.OperationContext.Current%2A> обеспечивает доступ к информации о контексте, в котором выполняется операция. <xref:System.ServiceModel.OperationContext> аналогичен классам <xref:System.Web.HttpContext> и <xref:System.EnterpriseServices.ContextUtil>.  
  
## <a name="hosting"></a>Размещение  
 Веб-службы ASP.NET компилируются в сборку библиотеки классов. Формируется файл, называемый файлом службы, который имеет расширение ASMX и содержит директиву `@ WebService`. Эта директива идентифицирует класс, содержащий код для службы и сборку, в которой он находится.  
  
```  
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>  
```  
  
 Файл службы копируется в корень приложения ASP.NET в службах IIS, а сборка копируется в подкаталог \bin этого корня приложения. После этого приложение будет доступно по URL-адресу файла службы в корне приложения.  
  
 Службы WCF могут легко быть размещены в IIS 5.1 или 6.0, процесс активации Windows Service (WAS), включенный в состав IIS 7.0, и в любом приложении .NET. Чтобы службу можно было разместить в IIS 5.1 или 6.0, в качестве транспортного протокола связи она должна использовать HTTP.  
  
 Чтобы разместить службу в IIS 5.1, 6.0 или в WAS, выполните следующие действия.  
  
1.  Скомпилируйте тип службы в сборку библиотеки классов.  
  
2.  Создайте файл службы с расширением SVC с директивой `@ ServiceHost` для идентификации типа службы:  
  
    ```  
    <%@ServiceHost language="c#" Service="MyService" %>  
    ```  
  
3.  Скопируйте файл службы в виртуальный каталог, а сборку в подкаталог \bin этого виртуального каталога.  
  
4.  Скопируйте файл конфигурации в виртуальный каталог и назовите его Web.config.  
  
 После этого приложение будет доступно по URL-адресу файла службы в корне приложения.  
  
 Для размещения службы WCF в приложении .NET, скомпилируйте тип службы в сборку библиотеки классов ссылается приложение и Запрограммируйте приложение на размещение службы с помощью <xref:System.ServiceModel.ServiceHost> класса. Ниже приведен простой пример требуемого программирования:  
  
```  
string httpBaseAddress = "http://www.contoso.com:8000/";  
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";  
  
Uri httpBaseAddressUri = new Uri(httpBaseAddress);  
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);  
  
Uri[] baseAdresses = new Uri[] {   
 httpBaseAddressUri,  
 tcpBaseAddressUri};  
  
using(ServiceHost host = new ServiceHost(  
typeof(Service), //"Service" is the name of the service type baseAdresses))  
{  
     host.Open();  
  
     […] //Wait to receive messages  
     host.Close();  
}  
```  
  
 В этом примере показано задание адресов для одного или нескольких транспортных протоколов при построении объекта <xref:System.ServiceModel.ServiceHost>. Эти адреса называются базовыми адресами.  
  
 Адрес, предоставляемый любой конечной точки службы WCF является адресом относительно базового адреса узла конечной точки. Узел размещения может иметь по одному базовому адресу для каждого транспортного протокола связи. В приведенном выше примере файла конфигурации выбранная для конечной точки привязка <xref:System.ServiceModel.BasicHttpBinding> предполагает использование в качестве транспорта протокола HTTP, поэтому адрес конечной точки — `EchoService`— рассматривается относительно базового HTTP-адреса узла. В случае узла в предыдущем примере, базовый адрес HTTP-это http://www.contoso.com:8000/. Для службы, размещенной в IIS или WAS, базовый адрес - это URL-адрес файла службы для этой службы.  
  
 Можно сделать только службы, размещенные в IIS или WAS и у которого должны быть настроены HTTP как транспортный протокол, чтобы использовать режим совместимости WCF ASP.NET. Для включения этого режима необходимо выполнить следующие шаги.  
  
1.  Программист должен добавить атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> в тип службы и указать, что режим совместимости с ASP.NET допускается либо требуется.  
  
    ```  
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(  
          RequirementsMode=AspNetCompatbilityRequirementsMode.Require)]  
    public class DerivativesCalculatorServiceType: IDerivativesCalculator  
    ```  
  
2.  Администратор должен настроить приложение на использование режима совместимости с ASP.NET.  
  
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
  
     Приложения WCF можно также настроить на использование ASMX расширения для своих файлов службы вместо SVC.  
  
    ```xml  
    <system.web>  
         <compilation>  
          <compilation debug="true">  
          <buildProviders>  
           <remove extension=".asmx"/>  
           <add extension=".asmx"   
            type="System.ServiceModel.ServiceBuildProvider,   
            Systemm.ServiceModel,   
            Version=3.0.0.0,   
            Culture=neutral,   
            PublicKeyToken=b77a5c561934e089" />  
          </buildProviders>  
          </compilation>  
         </compilation>  
    </system.web>  
    ```  
  
     Этот параметр позволяет сократить внесения изменений клиенты, настроенные для использования URL-адреса службы ASMX-файлов при изменении службы для использования WCF.  
  
## <a name="client-development"></a>Разработка клиентов  
 Клиенты для веб-служб ASP.NET формируются с помощью программы командной строки WSDL.exe, которая предоставляет URL-адрес ASMX-файла в качестве входных данных. Соответствующие средства, предоставляемые WCF — [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Она формирует модуль кода с определением контракта службы и определением класса клиента WCF. Кроме того, она формирует файл конфигурации с адресом и привязкой службы.  
  
 При программировании клиента удаленной службы обычно рекомендуется программировать в соответствии с асинхронной моделью. Код, формируемый программой WSDL.exe, по умолчанию всегда предусматривает и синхронную, и асинхронную модели. Код, сгенерированный [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) можно предоставить либо шаблон. По умолчанию предусматривается синхронная модель. При выполнении программы с переключателем `/async` сформированный код предусматривает асинхронную модель.  
  
 Нет никакой гарантии, что имена в классов клиента WCF, созданные ASP. NET средства WSDL.exe, по умолчанию совпадают с именами в классов клиента WCF, созданные с помощью средства Svcutil.exe. В частности, имена свойств классов, которые должны сериализоваться с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>, в формируемом программой Svcutil.exe коде по умолчанию получают суффикс "Property", который отсутствует в коде, формируемом WSDL.exe.  
  
## <a name="message-representation"></a>Представление сообщений  
 Заголовки сообщений SOAP, отправляемых и получаемых веб-службами ASP.NET, можно настроить. Из класса <xref:System.Web.Services.Protocols.SoapHeader> наследуется класс для определения структуры заголовка, после чего применяется атрибут <xref:System.Web.Services.Protocols.SoapHeaderAttribute>, чтобы указать на присутствие заголовка.  
  
```  
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
  
 WCF предоставляет атрибуты, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, и <xref:System.ServiceModel.MessageBodyMemberAttribute> для описания структуры сообщений SOAP, отправляемых и получаемых службой.  
  
```  
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
public class ItemMesage  
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
  
 Этот синтаксис дает явное представление структуры сообщений, тогда как в веб-службе ASP.NET структура сообщений подразумевается в коде. Кроме того, в синтаксисе ASP.NET заголовки сообщений представляются как свойства службы, таких как `ProtocolHeader` свойство в предыдущем примере, тогда как в синтаксисе WCF они представляются более точно как свойства сообщений. Кроме того WCF позволяет заголовки сообщений для добавления конфигурации конечных точек.  
  
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
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 WSDL-код, формируемый ASP.NET для службы, можно настраивать. Настройка производится путем создания класса, производного от <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, для добавления элементов в WSDL-код.  
  
 Передача запроса HTTP GET с запросом "WSDL" на SVC-файл службы WCF с конечной точкой HTTP, размещенной в IIS 51, 6.0 или WAS заставляет ответ WSDL-код для описания службы WCF. Передача запроса HTTP-GET с запросом «WSDL» на базовый HTTP-адрес службы, размещенной в приложении .NET, имеет тот же эффект, если параметр httpGetEnabled имеет значение true.  
  
 Однако WCF также отвечает на запросы WS-MetadataExchange WSDL-код, сформированный для описания службы. Веб-службы ASP.NET не располагают встроенной поддержкой запросов WS-MetadataExchange.  
  
 WSDL-код, создающий WCF, очень гибко настраивается. Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> предоставляет некоторые средства для настройки WSDL-кода. WCF также может использоваться для формирования WSDL-кода, но вместо этого использовать статического WSDL-файла по заданному URL-АДРЕСУ.  
  
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
  
 В службах WCF необработанные исключения не возвращаются клиентам виде ошибок SOAP во избежание случайного раскрытия через исключения конфиденциальные сведения. Предусмотрен параметр конфигурации для возвращения необработанных исключений клиентам в целях отладки.  
  
 Для возвращения ошибок SOAP клиентам можно вызывать исключения универсального типа - <xref:System.ServiceModel.FaultException%601> - используя в качестве универсального типа тип контракта данных. Также можно добавлять в операции атрибуты <xref:System.ServiceModel.FaultContractAttribute> для указания того, какие ошибки могут быть выданы операцией.  
  
```  
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
  
```  
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
  
```  
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
  
 В данном случае — тип службы, `TradingSystem`, имеет <xref:System.ServiceModel.ServiceBehaviorAttribute> , указывающий, что все вызовы из того же экземпляра клиента WCF, направляются на один экземпляр типа службы.  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class TradingSystem: ITradingService  
```  
  
 Класс, `DealData`, определяет состояние, к которому может обращаться любой код, выполняемый в одном и том же экземпляре типа службы.  
  
```  
internal class DealData: IExtension<InstanceContext>  
{  
 public string DealIdentifier = null;  
 public Trade[] Trades = null;  
}  
```  
  
 В коде типа службы, реализующем одну из операций контракта службы, к состоянию текущего экземпляра типа службы добавляется объект состояния `DealData`.  
  
```  
string ITradingService.BeginDeal()  
{  
 string dealIdentifier = Guid.NewGuid().ToString();  
 DealData state = new DealData(dealIdentifier);  
 OperationContext.Current.InstanceContext.Extensions.Add(state);  
 return dealIdentifier;  
}  
```  
  
 Этот объект состояния затем может быть извлечен и изменен кодом, реализующим другую операцию контракта службы.  
  
```  
void ITradingService.AddTrade(Trade trade)  
{  
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();  
 dealData.AddTrade(trade);  
}  
```  
  
 В то время как ASP.NET позволяет контролировать где информации о состоянии в <xref:System.Web.HttpContext> класса фактически хранятся, WCF, по крайней мере в первоначальной версии, не предусмотрена возможность управления через хранения расширяемых объектов. Это является очень основная причина, по выбору режима совместимости с ASP.NET для службы WCF. Если настраиваемое управление состоянием является обязательным условием, выбор режима совместимости с ASP.NET позволяет использовать средства класса <xref:System.Web.HttpContext> в точности так, как они используются в ASP.NET, а также настраивать место хранения информации о состоянии с помощью класса <xref:System.Web.HttpContext>.  
  
## <a name="security"></a>Безопасность  
 Для защиты веб-служб ASP.NET используются те же механизмы, что и для защиты любого приложения IIS. Поскольку приложения WCF могут размещаться не только в службах IIS, но также и в любой исполняемый файл .NET, механизмы защиты приложений WCF должны быть независимы от средств IIS. Тем не менее средства, предоставляемые веб-служб ASP.NET также доступны для служб WCF, работающих в режиме совместимости с ASP.NET.  
  
### <a name="security-authentication"></a>Безопасность: проверка подлинности  
 Службы IIS предоставляют средства для управления доступом к приложениям, позволяющие выбрать либо анонимный доступ, либо один из ряда режимов проверки подлинности: проверка подлинности Windows, дайджест-проверка подлинности, обычная проверка подлинности и проверка подлинности по паспорту .NET Passport. Вариант с проверкой подлинности Windows можно использовать для управления доступом к веб-службам ASP.NET. Однако при размещении приложений WCF в IIS, необходимо настроить IIS на разрешение анонимного доступа к приложению, чтобы проверкой подлинности можно управлять через службу WCF, которая поддерживает проверку подлинности Windows, помимо других возможностей. Другие встроенные средства включают маркеры имени пользователя, сертификаты X.509, маркеры SAML и карту CardSpace; также можно определять пользовательские механизмы проверки подлинности.  
  
### <a name="security-impersonation"></a>Безопасность: олицетворение  
 ASP.NET предоставляет элемент удостоверения, посредством которого веб-служба ASP.NET может олицетворять определенного пользователя или любого пользователя, учетные данные которого переданы в текущем запросе. Этот элемент может использоваться для настройки олицетворения в приложениях WCF, работающих в режиме совместимости с ASP.NET.  
  
 Система конфигурации WCF предоставляет собственный элемент удостоверения для задания определенного пользователя для олицетворения. Кроме того клиенты и службы WCF можно независимо настроить для олицетворения. Клиенты можно настроить на олицетворение текущего пользователя при передаче запросов.  
  
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
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public void Receive(Message input)  
```  
  
### <a name="security-authorization-using-access-control-lists"></a>Безопасность: авторизация с использованием списков управления доступом  
 Для ограничения доступа к ASMX-файлам можно использовать списки управления доступом (ACL). Однако списки ACL для WCF SVC-файлов учитываются за исключением того, в режиме совместимости с ASP.NET.  
  
### <a name="security-role-based-authorization"></a>Безопасность: авторизация на основе ролей  
 Режим проверки подлинности Windows, предоставляемый службами IIS, можно использовать в сочетании с предусмотренным в языке конфигурации ASP.NET элементом авторизации для упрощения авторизации на основе ролей для веб-служб ASP.NET, основанных на группах Windows, которым назначены пользователи. В ASP.NET 2.0 появился более общий механизм авторизации на основе ролей: поставщики ролей.  
  
 Поставщики ролей - это классы, реализующие базовый интерфейс для отправки запросов о ролях, которым назначен пользователь, причем каждый поставщик ролей предназначен для извлечения этой информации из определенного источника. ASP.NET 2.0 предоставляет поставщик ролей, который может извлекать назначения ролей из базы данных Microsoft SQL Server, и еще один поставщик, способный извлекать назначения ролей из диспетчера авторизации Windows Server 2003.  
  
 Механизм поставщиков ролей фактически используется независимо от ASP.NET в любом приложении .NET, включая приложения WCF. Следующий пример конфигурации для приложения WCF показано, как использование поставщика ролей ASP выбирается с помощью параметра <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.  
  
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
  
### <a name="security-claims-based-authorization"></a>Безопасность: авторизация на основе утверждений  
 Одним из важнейших нововведений, появившихся WCF является хорошо проработанная поддержка авторизации доступа к защищенным ресурсам на основе утверждений. Утверждения состоят из типа, права и значения. В качестве примера можно привести водительское удостоверение: оно содержит ряд утверждений о своем предъявителе, одним из которых является дата рождения предъявителя. Тип этого утверждения - дата рождения, а значение утверждения - дата рождения водителя. Право, которое утверждение дает предъявителю, указывает, что предъявитель может делать со значением утверждения. В случае утверждения даты рождения водителя право состоит во владении: эта дата рождения принадлежит водителю, однако он не может, например, изменять ее. Авторизация на основе утверждений включает в себя авторизацию на основе ролей, поскольку роли являются одним из типов утверждений.  
  
 Авторизация на основе утверждений осуществляется путем сравнения набора утверждений с требованиями доступа к операции и предоставления доступа к операции или отказа в доступе к операции в зависимости от результатов этого сравнения. В WCF, можно указать класс использовать для выполнения авторизации на основе утверждений, еще раз путем присвоения значения для `ServiceAuthorizationManager` свойство <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.  
  
```xml  
<behaviors>  
     <behavior name='ServiceBehavior'>  
     <serviceAuthorization   
     serviceAuthorizationManagerType=  
                   'Service.AccessChecker, Service' />  
     </behavior>  
</behaviors>  
```  
  
 Классы, используемые для выполнения авторизации на основе утверждений, должны быть производными от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, в котором имеется только один метод для переопределения - `AccessCheck()`. WCF вызывает этот метод при каждом вызове операции службы и предоставляет <xref:System.ServiceModel.OperationContext> object, который содержит утверждения для пользователя в его `ServiceSecurityContext.AuthorizationContext` свойство. WCF выполняет работу, собирая утверждения о пользователе из всего массива данных, представленных пользователем для проверки подлинности, чего остается только оценить, достаточно ли этих утверждений для выполнения запрошенной операции.  
  
 Автоматически обрабатывает WCF утверждений из любого типа безопасности маркера очень значительное нововведение, поскольку это делает код для авторизации на основе утверждений полностью независимым от механизма проверки подлинности. В противоположность этому авторизация с использованием списков ACL или ролей в ASP.NET тесно связана с проверкой подлинности Windows.  
  
### <a name="security-confidentiality"></a>Безопасность: конфиденциальность  
 Конфиденциальность сообщений, отправляемых и принимаемых веб-службами ASP.NET, может быть обеспечена на уровне транспорта путем настройки приложения в IIS на использование протокола HTTPS. То же можно сделать для приложений WCF, размещенных в службах IIS. Тем не менее приложения WCF, размещенных вне IIS также может быть настроен на использование защищенного транспортного протокола. Более важно, приложения WCF можно также настроить для защиты сообщений перед их транспортировкой с использованием протокола WS-Security. Защита только тела сообщения с использованием WS-Security позволяет передавать его с соблюдением конфиденциальности в пункт назначения через посредников.  
  
## <a name="globalization"></a>Глобализация  
 Язык конфигурации ASP.NET позволяет задавать язык и региональные параметры для отдельных служб. WCF не поддерживает этот параметр конфигурации, за исключением того, в режиме совместимости с ASP.NET. Для локализации службы WCF, которая не использует режим совместимости с ASP.NET, скомпилируйте тип службы в специфические для языка и региональных параметров сборки и иметь отдельные конечные точки для конкретного языка и региональных параметров для каждого конкретного языка и региональных параметров сборки.  
  
## <a name="see-also"></a>См. также  
 [Сравнение веб-служб ASP.NET с веб-службами на основе WCF по назначению и используемым стандартам](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
