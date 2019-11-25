---
title: Суррогат DataContract
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: f08226d3d871caea2dea3eeaf1cd411557853e45
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976717"
---
# <a name="datacontract-surrogate"></a>Суррогат DataContract
В этом образце показано, каким образом такие процессы, как сериализация, десериализация, экспорт и импорт схемы, могут быть настроены при помощи заменяющего класса контракта данных. В этом примере показано, как использовать суррогат в сценарии клиента и сервера, в котором данные сериализуются и передаются между клиентом Windows Communication Foundation (WCF) и службой.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце используется следующий контракт службы.  
  
```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 Операция `AddEmployee` позволяет пользователям добавлять данные о новых сотрудниках, а операция `GetEmployee` поддерживает поиск сотрудников по имени.  
  
 В этих операциях используется следующий тип данных.  
  
```csharp
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 В типе `Employee` класс `Person` (показан в следующем образце кода) не может быть сериализован с помощью <xref:System.Runtime.Serialization.DataContractSerializer>, поскольку он не является допустимым классом контракта данных.  
  
```csharp
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 Можно применить атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу `Person`, но это не всегда возможно. Например, класс `Person` может быть определен в отдельной сборке, управлять которой невозможно.  
  
 С учетом этого ограничения одним из способов сериализации класса `Person` является его замена на другой класс, отмеченный атрибутом <xref:System.Runtime.Serialization.DataContractAttribute>, и копирование необходимых данных в новый класс. Целью является отображение класса `Person` как DataContract в сериализаторе <xref:System.Runtime.Serialization.DataContractSerializer>. Обратите внимание, что это один способ сериализации классов, отличных от классов контракта данных.  
  
 В этом образце класс `Person` логически заменяется на другой класс с именем `PersonSurrogated`.  
  
```csharp
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 Заменяющий класс контракта данных используется для обеспечения такой замены. Заменяющий класс контракта данных является классом, который реализует <xref:System.Runtime.Serialization.IDataContractSurrogate>. В этом образце класс `AllowNonSerializableTypesSurrogate` реализует этот интерфейс.  
  
 В реализации интерфейса первой задачей является установка сопоставления типов из класса `Person` с классом `PersonSurrogated`. Используется как во время сериализации, так и во время экспорта схемы. Такое сопоставление обеспечивается путем реализации метода <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29>.  
  
```csharp
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> сопоставляет экземпляр класса `Person` с экземпляром класса `PersonSurrogated` во время сериализации, как показано в следующем образце кода.  
  
```csharp
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> обеспечивает обратное сопоставление для десериализации, как показано в следующем образце кода.  
  
```csharp
public object GetDeserializedObject(object obj,   
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 Чтобы сопоставить контракт данных `PersonSurrogated` с существующим классом `Person` во время импорта схемы, в образце реализуется метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29>, как показано в следующем образце кода.  
  
```csharp
public Type GetReferencedTypeOnImport(string typeName,   
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 В следующем образце кода показано завершение реализации интерфейса <xref:System.Runtime.Serialization.IDataContractSurrogate>.  
  
```csharp
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,   
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,   
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 В этом образце заменяющий класс включается в ServiceModel с помощью атрибута `AllowNonSerializableTypesAttribute`. Разработчикам пришлось бы применить этот атрибут к контракту службы, как показано в контракте службы `IPersonnelDataService` выше. Этот атрибут реализует `IContractBehavior` и настраивает заменяющий класс в операциях методов `ApplyClientBehavior` и `ApplyDispatchBehavior`.  
  
 В этом случае необходимости в атрибуте нет. В этом образце он используется в демонстрационных целях. Пользователи могут также включить заменяющий класс вручную, добавив похожее поведение `IContractBehavior`, `IEndpointBehavior` или `IOperationBehavior` с использованием кода или конфигурации.  
  
 Реализация `IContractBehavior` ищет операции, в которых используется DataContract, проверяя в них наличие зарегистрированного поведения `DataContractSerializerOperationBehavior`. При его наличии она задает свойство `DataContractSurrogate` для этого поведения. В следующем образце кода показано, как это можно сделать. Задание заменяющего класса для этого поведения операции позволяет ему участвовать в сериализации и десериализации.  
  
```csharp
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 Чтобы подключить заменяющий класс для использования при создании метаданных, необходимо выполнить дополнительные действия. Одним из механизмов реализации этого является предоставление расширения `IWsdlExportExtension`, как показано в этом образце. Еще одним способом является непосредственное изменение `WsdlExporter`.  
  
 Атрибут `AllowNonSerializableTypesAttribute` реализует `IWsdlExportExtension` и `IContractBehavior`. В этом случае в качестве расширения может использоваться либо `IContractBehavior`, либо `IEndpointBehavior`. Реализация метода `IWsdlExportExtension.ExportContract` включает заменяющий класс путем его добавления в `XsdDataContractExporter`, используемый во время создания схемы для DataContract. В следующем фрагменте кода показано, как это сделать.  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 При выполнении образца клиент вызывает операцию AddEmployee после вызова операции GetEmployee, чтобы проверить, выполнен ли первый вызов успешно. Результат запроса операции GetEmployee отображается в окне консоли клиента. Операция сотрудника должна пройти, чтобы найти сотрудника и напечатать "Found".  
  
> [!NOTE]
> В этом примере показано, как подключить заменяющий класс для сериализации, десериализации и создания метаданных. В нем не показано, как подключить заменяющий класс для создания кода из метаданных. Чтобы увидеть пример того, как суррогат можно использовать для подключения к созданию клиентского кода, см. пример [пользовательской публикации WSDL](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) .  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать C# выпуск решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
