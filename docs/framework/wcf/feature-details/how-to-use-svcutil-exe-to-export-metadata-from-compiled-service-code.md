---
title: "Как использовать программу Svcutil.exe для экспорта метаданных из скомпилированного кода службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как использовать программу Svcutil.exe для экспорта метаданных из скомпилированного кода службы
При помощи Svcutil.exe можно экспортировать метаданные для служб, контрактов и типов данных в скомпилированных сборках, как показано далее.  
  
-   Для экспорта метаданных всех скомпилированных контрактов службы для набора сборок при помощи Svcutil.exe необходимо указать сборки как входные параметры.Это поведение установлено по умолчанию.  
  
-   Для экспорта метаданных скомпилированной службы для набора сборок при помощи Svcutil.exe необходимо указать сборку службы как входные параметры.Для указания имени конфигурации экспортируемой службы необходимо использовать параметр `/serviceName`.Svcutil.exe автоматически загружает файл конфигурации для указанной сборки исполняемого файла.  
  
-   Для экспорта всех типов контрактов данных внутри набора сборок используется параметр `/dataContractOnly`.  
  
> [!NOTE]
>  Для указания пути к файлам любых зависимых сборок используется параметр `/reference`.  
  
### Экспорт метаданных в скомпилированные контракты службы  
  
1.  Скомпилируйте реализации контракта службы в одну или несколько библиотек классов.1  
  
2.  Запустите Svcutil.exe в скомпилированных сборках.  
  
    > [!NOTE]
    >  Для указания пути к файлам любых зависимых сборок может понадобиться использование параметра `/reference`.  
  
    ```  
    svcutil.exe Contracts.dll  
    ```  
  
### Экспорт метаданных в скомпилированную службу  
  
1.  Скомпилируйте реализацию службы в исполняемую сборку.  
  
2.  Создайте файл конфигурации для исполняемого файла службы и добавьте конфигурацию службы.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3.  Чтобы указать имя конфигурации службы, необходимо запустить Svcutil.exe в скомпилированном исполняемом файле службы при помощи параметра `/serviceName`.  
  
    > [!NOTE]
    >  Для указания пути к файлам любых зависимых сборок может понадобиться использование параметра `/reference`.  
  
    ```  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### Экспорт метаданных в скомпилированные контракты данных  
  
1.  Скомпилируйте реализации контракта данных в одну или несколько библиотек классов.  
  
2.  Чтобы задать генерацию только метаданных для контрактов данных, запустите Svcutil.exe в скомпилированных сборках с параметром `/dataContract`.  
  
    > [!NOTE]
    >  Для указания пути к файлам любых зависимых сборок может понадобиться использование параметра `/reference`.  
  
    ```  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## Пример  
 В следующем примере показано, как генерировать метаданные для реализации и конфигурации простой службы.  
  
 Экспорт метаданных в контракт службы.  
  
```  
svcutil.exe Contracts.dll  
```  
  
 Экспорт метаданных в контракты данных.  
  
```  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 Экспорт метаданных в реализацию службы.  
  
```  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 `<path>` является путем к файлу Contracts.dll.  
  
```  
// The following service contract and data contracts are compiled into   
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
  
// The following service implementation is compiled into Service.exe.     
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
  
```  
  
## См. также  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)