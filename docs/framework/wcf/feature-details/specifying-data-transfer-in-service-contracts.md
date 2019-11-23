---
title: Задание передачи данных в контрактах служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
ms.openlocfilehash: 47544cf74b4fa09fd8ee868ea940ef24a453840e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834636"
---
# <a name="specifying-data-transfer-in-service-contracts"></a>Задание передачи данных в контрактах служб
Windows Communication Foundation (WCF) можно рассматривать как инфраструктуру обмена сообщениями. Операции служб могут получать сообщения, обрабатывать их и отправлять. Сообщения описываются с помощью контрактов операций. Например, рассмотрим следующий контракт:  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(string fromCity, string toCity);  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
  
    <OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
End Interface  
```  
  
 Операция `GetAirfare` принимает сообщение с информацией о `fromCity` и `toCity`, затем возвращает сообщение, содержащее число.  
  
 В этом разделе рассматриваются различные способы описания сообщений в контракте операции.  
  
## <a name="describing-messages-by-using-parameters"></a>Описание сообщений с помощью параметров  
 Простейший способ описания сообщений - с помощью списка параметров и возвращаемого значения. В приведенном выше примере строковые параметры `fromCity` и `toCity` используются для описания сообщения запроса, а возвращаемое значение типа "float" - для описания ответного сообщения. Если возвращаемое значение само по себе недостаточно для описания ответного сообщения, можно использовать выходные параметры. Например, следующая операция содержит строки `fromCity` и `toCity` в сообщении запроса и число с названием валюты в ответном сообщении:  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 Кроме того, используя ссылочные параметры, можно сделать параметр частью обоих сообщений (запроса и ответа). Параметры должны принадлежать к сериализуемому типу (преобразуемому в XML). По умолчанию для выполнения этого преобразования WCF использует компонент, именуемый классом <xref:System.Runtime.Serialization.DataContractSerializer>. Поддерживается большая часть типов-примитивов (таких как `int`, `string`, `float` и `DateTime`). Как правило, пользовательские типы должны иметь контракт данных. Дополнительные сведения см. [в разделе Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
```csharp
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
  
    [DataContract]  
    public class Itinerary  
    {  
        [DataMember]  
        public string fromCity;  
        [DataMember]  
        public string toCity;  
   }  
}  
```  
  
```vb  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
    <DataContract()>  
    Class Itinerary  
  
        <DataMember()>  
        Public fromCity As String  
        <DataMember()>  
        Public toCity As String  
    End Class  
End Interface  
```  
  
 Иногда объект `DataContractSerializer` не подходит для сериализации конкретных типов. WCF поддерживает альтернативный механизм сериализации, <xref:System.Xml.Serialization.XmlSerializer>, который также можно использовать для сериализации параметров. Сериализатор <xref:System.Xml.Serialization.XmlSerializer> позволяет более четко контролировать результирующий XML-код с помощью атрибутов, таких как `XmlAttributeAttribute`. Чтобы перейти на использование сериализатора <xref:System.Xml.Serialization.XmlSerializer> для определенной операции или для всей службы, примените к ней атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>. Например:  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    [XmlSerializerFormat]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
}  
public class Itinerary  
{  
    public string fromCity;  
    public string toCity;  
    [XmlAttribute]  
    public bool isFirstClass;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    <XmlSerializerFormat>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
End Interface  
  
Class Itinerary  
  
    Public fromCity As String  
    Public toCity As String  
    <XmlSerializerFormat()>  
    Public isFirstClass As Boolean  
End Class  
```  
  
 Дополнительные сведения см. [в разделе Использование класса XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md). Следует помнить, что задавать использование модуля <xref:System.Xml.Serialization.XmlSerializer> вручную (как показано выше) не рекомендуется, если для этого нет определенных причин, рассмотренных в этом разделе.  
  
 Изолировать имена параметров .NET от имен контрактов можно с помощью атрибута <xref:System.ServiceModel.MessageParameterAttribute>, а задать имя контракта - с помощью свойства `Name`. Например, следующий контракт операции эквивалентен приведенному в первом примере этого раздела.  
  
```csharp  
[OperationContract]  
public float GetAirfare(  
    [MessageParameter(Name="fromCity")] string originCity,  
    [MessageParameter(Name="toCity")] string destinationCity);  
```  
  
```vb  
<OperationContract()>  
  Function GetAirfare(<MessageParameter(Name := "fromCity")> fromCity As String, <MessageParameter(Name := "toCity")> toCity As String) As Double  
```  
  
## <a name="describing-empty-messages"></a>Описание пустых сообщений  
 Пустое сообщение запроса можно описать с помощью отсутствия входных и ссылочных параметров. Например, в C#:  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 Например, в VB.  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 Пустое сообщение ответа можно описать, указав тип `void` для возвращаемого значения и отсутствие входных и ссылочных параметров. Например, в  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 Это действие не является односторонней операцией, как например:  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 Операция `SetTemperatureStatus` возвращает пустое сообщение. Вместо него она может вернуть ошибку, если возникнет проблема при обработке входного сообщения. Операция `SetLightbulbStatus` не возвращает какое-либо значение. Эта операция никоим образом не может сообщить об ошибке.  
  
## <a name="describing-messages-by-using-message-contracts"></a>Описание сообщений с помощью контрактов сообщений  
 Иногда имеет смысл представить все сообщение одним типом. Хотя для этого можно использовать контракт данных, все же рекомендуется использовать контракт сообщений: это позволяет избежать чрезмерных уровней заключения в оболочку в результирующем XML-коде. Кроме того, контракты сообщений обеспечивают более полное управление результирующими сообщениями. Например, можно задать, какие именно сведения должны находиться в тексте сообщения и какие в заголовке. В следующем примере показано использование контрактов сообщений.  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    GetAirfareResponse GetAirfare(GetAirfareRequest request);  
}  
  
[MessageContract]  
public class GetAirfareRequest  
{  
    [MessageHeader] public DateTime date;  
    [MessageBodyMember] public Itinerary itinerary;  
}  
  
[MessageContract]  
public class GetAirfareResponse  
{  
    [MessageBodyMember] public float airfare;  
    [MessageBodyMember] public string currency;  
}  
  
[DataContract]  
public class Itinerary  
{  
    [DataMember] public string fromCity;  
    [DataMember] public string toCity;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    Function GetAirfare(request As GetAirfareRequest) As GetAirfareResponse  
End Interface  
  
<MessageContract()>  
Public Class GetAirfareRequest  
    <MessageHeader()>   
    Public Property date as DateTime  
    <MessageBodyMember()>  
    Public Property itinerary As Itinerary  
End Class  
  
<MessageContract()>  
Public Class GetAirfareResponse  
    <MessageBodyMember()>  
    Public Property airfare As Double  
    <MessageBodyMember()> Public Property currency As String  
End Class  
  
<DataContract()>  
Public Class Itinerary  
    <DataMember()> Public Property fromCity As String  
    <DataMember()> Public Property toCity As String  
End Class  
```  
  
 Дополнительные сведения см. [в разделе Использование контрактов сообщений](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
 В приведенном выше примере класс <xref:System.Runtime.Serialization.DataContractSerializer> используется по умолчанию. Класс <xref:System.Xml.Serialization.XmlSerializer> также можно использовать с контрактами сообщений. Для этого примените атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute> к операции или к контракту и используйте типы, совместимые с классом <xref:System.Xml.Serialization.XmlSerializer>, в заголовках сообщения и элементах тела сообщения.  
  
## <a name="describing-messages-by-using-streams"></a>Описание сообщений с помощью потоков  
 Еще один способ описания сообщений в операциях - использование класса <xref:System.IO.Stream> (или одного из производных от него классов) в контракте операции или в качестве элемента тела контракта сообщения (в этом случае он должен быть единственным элементом). Для входящих сообщений необходимо использовать тип `Stream`: производные классы использовать не допускается.  
  
 Вместо вызова сериализатора WCF извлекает данные из потока и помещает их непосредственно в исходящее сообщение или получает данные из входящего сообщения и помещает их непосредственно в поток. В следующем образце показано использование потоков.  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 Нельзя совмещать потоковые данные (`Stream`) с непотоковыми в одном теле сообщения. Используйте контракт сообщения, чтобы поместить дополнительные данные в заголовок сообщения. В следующем примере показано неправильное использование потоков при определении контракта операции.  
  
```csharp  
//Incorrect:  
// [OperationContract]  
// public void UploadFile (string fileName, Stream fileData);  
```  
  
```vb  
'Incorrect:  
    '<OperationContract()>  
    Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
```  
  
 В следующем образце показано правильное использование потоков при определении контракта операции.  
  
```csharp  
[OperationContract]  
public void UploadFile (UploadFileMessage message);  
//code omitted  
[MessageContract]  
public class UploadFileMessage  
{  
    [MessageHeader] public string fileName;  
    [MessageBodyMember] public Stream fileData;  
}  
```  
  
```vb  
<OperationContract()>  
Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
'Code Omitted  
<MessageContract()>  
Public Class UploadFileMessage  
   <MessageHeader()>  
    Public Property fileName As String  
    <MessageBodyMember()>  
    Public Property fileData As Stream  
End Class  
```  
  
 Дополнительные сведения см. в разделе [большие данные и потоковая передача](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
## <a name="using-the-message-class"></a>Использование класса сообщений  
 Чтобы обеспечить полный программный контроль над получаемыми или отправляемыми сообщениями, можно использовать класс <xref:System.ServiceModel.Channels.Message> напрямую, как показано в следующем примере кода.  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 Это расширенный сценарий, подробно описанный в разделе [использование класса Message](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).  
  
## <a name="describing-fault-messages"></a>Описание сообщений об ошибках  
 Помимо сообщений, описываемых возвращаемыми значениями и выходными или ссылочными параметрами, любая неодносторонняя операция может возвращать не менее двух возможных значений: нормальное ответное сообщение и сообщение об ошибке. Рассмотрим следующий контракт операции.  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 Эта операция может возвращать либо нормальное сообщение, содержащее число `float`, либо сообщение об ошибке, содержащее код ошибки и ее описание. Для этого следует предусмотреть вызов исключения <xref:System.ServiceModel.FaultException> при реализации службы.  
  
 Можно указать дополнительные сообщения об ошибках с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute>. Необходима возможность сериализации дополнительных ошибок с помощью кода <xref:System.Runtime.Serialization.DataContractSerializer>, как показано в следующем примере.  
  
```csharp  
[OperationContract]  
[FaultContract(typeof(ItineraryNotAvailableFault))]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
  
//code omitted  
  
[DataContract]  
public class ItineraryNotAvailableFault  
{  
    [DataMember]  
    public bool IsAlternativeDateAvailable;  
  
    [DataMember]  
    public DateTime alternativeSuggestedDate;  
}  
```  
  
```vb  
<OperationContract()>  
<FaultContract(GetType(ItineraryNotAvailableFault))>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime) As Double  
  
'Code Omitted  
<DataContract()>  
Public Class  
  <DataMember()>  
  Public Property IsAlternativeDateAvailable As Boolean  
  <DataMember()>  
  Public Property alternativeSuggestedDate As DateTime  
End Class  
```  
  
 Эти дополнительные ошибки можно создать вызовом исключения <xref:System.ServiceModel.FaultException%601> с соответствующим типом данных контракта. Дополнительные сведения см. в разделе [обработка исключений и ошибок](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
 Использовать класс <xref:System.Xml.Serialization.XmlSerializer> для описания ошибок не допускается. Атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute> не влияет на контракты ошибок.  
  
## <a name="using-derived-types"></a>Использование производных типов  
 Иногда имеет смысл использовать базовый тип в контракте операции или сообщения, а затем (при фактическом вызове операции) производный тип. В этом случае необходимо использовать либо атрибут <xref:System.ServiceModel.ServiceKnownTypeAttribute>, либо некий альтернативный механизм, позволяющий использовать производные типы. Рассмотрим следующую операцию.  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 Предположим, что два типа, `Book` и `Magazine`, унаследованы от `LibraryItem`. Чтобы использовать их в операции `IsLibraryItemAvailable`, можно изменить ее следующим образом:  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 Или же можно воспользоваться атрибутом <xref:System.Runtime.Serialization.KnownTypeAttribute>, если атрибут по умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> уже используется, как показано в следующем примере кода.  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
  
// code omitted   
  
[DataContract]  
[KnownType(typeof(Book))]  
[KnownType(typeof(Magazine))]  
public class LibraryItem  
{  
    //code omitted  
}  
```  
  
```vb  
<OperationContract()>  
Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
  
'Code Omitted  
<DataContract()>  
<KnownType(GetType(Book))>  
<KnownType(GetType(Magazine))>  
Public Class LibraryItem  
  'Code Omitted  
End Class  
```  
  
 Для этого примените атрибут <xref:System.Xml.Serialization.XmlIncludeAttribute> при использовании <xref:System.Xml.Serialization.XmlSerializer>.  
  
 Атрибут <xref:System.ServiceModel.ServiceKnownTypeAttribute> можно применить к операции или ко всей службе. Он принимает либо тип, либо имя метода, при вызове которого возвращается список известных типов (подобно атрибуту <xref:System.Runtime.Serialization.KnownTypeAttribute>). Дополнительные сведения см. в статье о [известных типах контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="specifying-the-use-and-style"></a>Указание назначения и стиля  
 Для описания служб с помощью языка WSDL наиболее часто используются следующие две службы: Document и RPC (удаленный вызов процедуры). В стиле Document тело сообщения полностью описывается с помощью схемы, а в языке WSDL различные части тела сообщения описываются ссылками на элементы в этой схеме. В стиле RPC код WSDL ссылается на тип схемы для каждой части сообщения, а не элемент. В некоторых случаях необходимо выбрать один из этих типов вручную. Для этого можно применить атрибут <xref:System.ServiceModel.DataContractFormatAttribute> и задать свойство `Style` (когда используется <xref:System.Runtime.Serialization.DataContractSerializer>) или задать `Style` атрибуту <xref:System.ServiceModel.XmlSerializerFormatAttribute> (когда используется <xref:System.Xml.Serialization.XmlSerializer>).  
  
 Кроме того, <xref:System.Xml.Serialization.XmlSerializer> поддерживает две формы сериализованного XML: `Literal` и `Encoded`. `Literal` является наиболее часто принятой формой, а является единственной формой, которую поддерживает <xref:System.Runtime.Serialization.DataContractSerializer>. `Encoded` является устаревшей формой, описанной в разделе 5 спецификации SOAP, и не рекомендуется для новых служб. Чтобы перейти в режим `Encoded`, задайте свойству `Use` атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute> значение `Encoded`.  
  
 В большинстве случаев лучше не изменять параметры по умолчанию для свойств `Style` и `Use`.  
  
## <a name="controlling-the-serialization-process"></a>Управление процессом сериализации  
 Сериализацию данных можно настраивать различными способами.  
  
### <a name="changing-server-serialization-settings"></a>Изменение параметров сериализации для сервера  
 Если используется сериализатор по умолчанию <xref:System.Runtime.Serialization.DataContractSerializer>, можно управлять некоторыми аспектами процесса сериализации в службе путем применения к ней атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute>. В частности, с помощью свойства `MaxItemsInObjectGraph` можно задать максимальную квоту на количество объектов, десериализуемых с помощью <xref:System.Runtime.Serialization.DataContractSerializer>. Можно использовать свойство `IgnoreExtensionDataObject` для отключения функции полной совместимости управления версиями. Дополнительные сведения о квотах см. в разделе [Вопросы безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md). Дополнительные сведения о циклической активации см. в разделе [контракты данных с прямыми совместимостью](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
```csharp  
[ServiceBehavior(MaxItemsInObjectGraph=100000)]  
public class MyDataService:IDataService  
{  
    public DataPoint[] GetData()  
    {  
       // Implementation omitted  
    }  
}  
```  
  
```vb  
<ServiceBehavior(MaxItemsInObjectGraph:=100000)>  
Public Class MyDataService Implements IDataService  
  
    Function GetData() As DataPoint()  
         ‘ Implementation omitted  
    End Function  
End Interface  
```  
  
### <a name="serialization-behaviors"></a>Поведения сериализации  
 В WCF доступны два поведения: <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> и <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>, которые автоматически подключаются в зависимости от того, какой сериализатор используется для определенной операции. Поскольку эти поведения применяются автоматически, о них обычно можно не беспокоиться.  
  
 Впрочем, у поведения `DataContractSerializerOperationBehavior` имеются свойства `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject` и `DataContractSurrogate`, позволяющие настроить процесс сериализации. Назначение первых двух из вышеперечисленных свойств аналогично рассмотренному в предыдущем разделе. С помощью свойства `DataContractSurrogate` можно включить суррогаты контрактов данных - мощный механизм настройки и расширения процесса сериализации. Дополнительные сведения см. в разделе [суррогаты контракта данных](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).  
  
 С помощью поведения `DataContractSerializerOperationBehavior` можно настроить сериализацию как для клиента, так и для сервера. В следующем примере показано, как увеличить квоту `MaxItemsInObjectGraph` для клиента.  
  
```csharp  
ChannelFactory<IDataService> factory = new ChannelFactory<IDataService>(binding, address);  
foreach (OperationDescription op in factory.Endpoint.Contract.Operations)  
{  
    DataContractSerializerOperationBehavior dataContractBehavior =  
                op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
    if (dataContractBehavior != null)  
    {  
        dataContractBehavior.MaxItemsInObjectGraph = 100000;  
    }  
}  
IDataService client = factory.CreateChannel();  
```  
  
```vb  
Dim factory As ChannelFactory(Of IDataService) = New ChannelFactory(Of IDataService)(binding, address)  
For Each op As OperationDescription In factory.Endpoint.Contract.Operations  
        Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
        If dataContractBehavior IsNot Nothing Then  
            dataContractBehavior.MaxItemsInObjectGraph = 100000  
        End If  
     Next  
    Dim client As IDataService = factory.CreateChannel  
```  
  
Ниже приведен эквивалентный код службы в собственном размещении:
  
```csharp  
ServiceHost serviceHost = new ServiceHost(typeof(IDataService))  
foreach (ServiceEndpoint ep in serviceHost.Description.Endpoints)  
{  
foreach (OperationDescription op in ep.Contract.Operations)  
{  
        DataContractSerializerOperationBehavior dataContractBehavior =  
           op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
        if (dataContractBehavior != null)  
        {  
            dataContractBehavior.MaxItemsInObjectGraph = 100000;  
        }  
}  
}  
serviceHost.Open();  
```  
  
```vb  
Dim serviceHost As ServiceHost = New ServiceHost(GetType(IDataService))  
        For Each ep As ServiceEndpoint In serviceHost.Description.Endpoints  
            For Each op As OperationDescription In ep.Contract.Operations  
                Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
  
                If dataContractBehavior IsNot Nothing Then  
                    dataContractBehavior.MaxItemsInObjectGraph = 100000  
                End If  
            Next  
        Next  
        serviceHost.Open()  
```  
  
 Если клиент размещен в Интернете, необходимо создать новый класс, производный от `ServiceHost`, и подключить его с помощью фабрики узла служб.  
  
### <a name="controlling-serialization-settings-in-configuration"></a>Управление параметрами сериализации в конфигурации  
 Параметры `MaxItemsInObjectGraph` и `IgnoreExtensionDataObject` можно изменять с помощью конфигурации, используя конечную точку `dataContractSerializer` или поведение службы, как показано в следующем примере.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="LargeQuotaBehavior">  
                    <dataContractSerializer  
                      maxItemsInObjectGraph="100000" />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <client>  
            <endpoint address="http://example.com/myservice"  
                  behaviorConfiguration="LargeQuotaBehavior"  
                binding="basicHttpBinding" bindingConfiguration=""   
                            contract="IDataService"  
                name="" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a>Сериализация общих типов, сохранение графов объектов и пользовательские сериализаторы  
 <xref:System.Runtime.Serialization.DataContractSerializer> при сериализации использует имена контрактов данных, а не имена типов .NET. Это соответствует принципам сервисноориентированной архитектуры и повышает степень гибкости, поскольку типы .NET могут изменяться, не затрагивая при этом сетевой контракт. В редких случаях имеет смысл сериализовать имена типов .NET, обеспечив таким образом тесное соединение клиента и сервера (подобно технологии удаленного взаимодействия платформы .NET Framework). Это не рекомендуемый подход, за исключением редких случаев, которые обычно возникают при переходе на WCF из .NET Framework удаленного взаимодействия. В этом случае необходимо использовать класс <xref:System.Runtime.Serialization.NetDataContractSerializer> вместо класса <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 <xref:System.Runtime.Serialization.DataContractSerializer> обычно сериализует графы объектов как деревья объектов. А именно, если один объект указан неоднократно, он сериализуется неоднократно. Рассмотрим, к примеру, экземпляр класса `PurchaseOrder`, имеющий два поля типа Address с именами `billTo` и `shipTo`. Если оба поля заданы одному и тому же экземпляру класса Address, после сериализации и десериализации получится два идентичных экземпляра этого класса. Это происходит из-за отсутствия стандартного (и поддерживающего взаимодействие) способа представления графов объектов в XML (за исключением стандарта предыдущих версий с кодировкой SOAP, используемого в сериализаторе <xref:System.Xml.Serialization.XmlSerializer>, как указано в предыдущем разделе о `Style` и `Use`). Сериализация графов объектов как деревьев имеет определенные преимущества: например, невозможность сериализации графов с циклическими ссылками. Иногда требуется переключиться на истинную сериализацию графов объектов, даже несмотря на потерю возможностей взаимодействия. Это достигается с помощью сериализатора <xref:System.Runtime.Serialization.DataContractSerializer>, созданного с параметром `preserveObjectReferences`, имеющим значение `true`.  
  
 Иногда встроенных сериализаторов бывает недостаточно для прорабатываемого сценария. В большинстве случаев все же сохраняется возможность использовать абстракцию <xref:System.Runtime.Serialization.XmlObjectSerializer>, от которой наследуются оба сериализатора (<xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.NetDataContractSerializer>).  
  
 Во всех трех предыдущих случаях (сохранение типов .NET, сохранение графов объектов и сериализация на базе пользовательского сериализатора `XmlObjectSerializer`) требуется подключить пользовательский сериализатор. Для этого выполните следующие действия.  
  
1. Самостоятельно составьте код поведения, наследуемого от класса <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.  
  
2. Переопределите два метода `CreateSerializer` так, чтобы они возвращали ваш сериализатор (либо <xref:System.Runtime.Serialization.NetDataContractSerializer>, т. е. сериализатор <xref:System.Runtime.Serialization.DataContractSerializer>, у которого для `preserveObjectReferences` задано значение `true`, либо полностью созданный вами сериализатор <xref:System.Runtime.Serialization.XmlObjectSerializer>).  
  
3. Прежде чем открывать узел службы или создавать канал клиента, удалите существующее поведение <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> и подключите производный пользовательский класс, созданный на предыдущих этапах.  
  
 Дополнительные сведения о дополнительных понятиях сериализации см. в разделе [сериализация и десериализация](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).  
  
## <a name="see-also"></a>См. также:

- [Использование класса XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)
- [Практическое руководство. Включение потоковой передачи](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
- [Практическое руководство. Создание базового контракта данных для класса или структуры](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
