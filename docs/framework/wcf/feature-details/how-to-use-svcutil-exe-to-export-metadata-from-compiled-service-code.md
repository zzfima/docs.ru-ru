---
title: "Практическое руководство. Использование программы Svcutil.exe для экспорта метаданных из скомпилированного кода службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 444fab903683b952d1a8c312c3f6032be880da68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="8908d-102">Практическое руководство. Использование программы Svcutil.exe для экспорта метаданных из скомпилированного кода службы</span><span class="sxs-lookup"><span data-stu-id="8908d-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>
<span data-ttu-id="8908d-103">При помощи Svcutil.exe можно экспортировать метаданные для служб, контрактов и типов данных в скомпилированных сборках, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="8908d-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
-   <span data-ttu-id="8908d-104">Для экспорта метаданных всех скомпилированных контрактов службы для набора сборок при помощи Svcutil.exe необходимо указать сборки как входные параметры.</span><span class="sxs-lookup"><span data-stu-id="8908d-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="8908d-105">Это поведение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8908d-105">This is the default behavior.</span></span>  
  
-   <span data-ttu-id="8908d-106">Для экспорта метаданных скомпилированной службы для набора сборок при помощи Svcutil.exe необходимо указать сборку службы как входные параметры.</span><span class="sxs-lookup"><span data-stu-id="8908d-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="8908d-107">Для указания имени конфигурации экспортируемой службы необходимо использовать параметр `/serviceName`.</span><span class="sxs-lookup"><span data-stu-id="8908d-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="8908d-108">Svcutil.exe автоматически загружает файл конфигурации для указанной сборки исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="8908d-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
-   <span data-ttu-id="8908d-109">Для экспорта всех типов контрактов данных внутри набора сборок используется параметр `/dataContractOnly`.</span><span class="sxs-lookup"><span data-stu-id="8908d-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8908d-110">Для указания пути к файлам любых зависимых сборок используется параметр `/reference`.</span><span class="sxs-lookup"><span data-stu-id="8908d-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="8908d-111">Экспорт метаданных в скомпилированные контракты службы</span><span class="sxs-lookup"><span data-stu-id="8908d-111">To export metadata for compiled service contracts</span></span>  
  
1.  <span data-ttu-id="8908d-112">Скомпилируйте реализации контракта службы в одну или несколько библиотек классов.1</span><span class="sxs-lookup"><span data-stu-id="8908d-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2.  <span data-ttu-id="8908d-113">Запустите Svcutil.exe в скомпилированных сборках.</span><span class="sxs-lookup"><span data-stu-id="8908d-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8908d-114">Для указания пути к файлам любых зависимых сборок может понадобиться использование параметра `/reference`.</span><span class="sxs-lookup"><span data-stu-id="8908d-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="8908d-115">Экспорт метаданных в скомпилированную службу</span><span class="sxs-lookup"><span data-stu-id="8908d-115">To export metadata for a compiled service</span></span>  
  
1.  <span data-ttu-id="8908d-116">Скомпилируйте реализацию службы в исполняемую сборку.</span><span class="sxs-lookup"><span data-stu-id="8908d-116">Compile your service implementation into an executable assembly.</span></span>  
  
2.  <span data-ttu-id="8908d-117">Создайте файл конфигурации для исполняемого файла службы и добавьте конфигурацию службы.</span><span class="sxs-lookup"><span data-stu-id="8908d-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
    ```xml  
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
  
3.  <span data-ttu-id="8908d-118">Чтобы указать имя конфигурации службы, необходимо запустить Svcutil.exe в скомпилированном исполняемом файле службы при помощи параметра `/serviceName`.</span><span class="sxs-lookup"><span data-stu-id="8908d-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8908d-119">Для указания пути к файлам любых зависимых сборок может понадобиться использование параметра `/reference`.</span><span class="sxs-lookup"><span data-stu-id="8908d-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="8908d-120">Экспорт метаданных в скомпилированные контракты данных</span><span class="sxs-lookup"><span data-stu-id="8908d-120">To export metadata for compiled data contracts</span></span>  
  
1.  <span data-ttu-id="8908d-121">Скомпилируйте реализации контракта данных в одну или несколько библиотек классов.</span><span class="sxs-lookup"><span data-stu-id="8908d-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2.  <span data-ttu-id="8908d-122">Чтобы задать генерацию только метаданных для контрактов данных, запустите Svcutil.exe в скомпилированных сборках с параметром `/dataContract`.</span><span class="sxs-lookup"><span data-stu-id="8908d-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8908d-123">Для указания пути к файлам любых зависимых сборок может понадобиться использование параметра `/reference`.</span><span class="sxs-lookup"><span data-stu-id="8908d-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="8908d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8908d-124">Example</span></span>  
 <span data-ttu-id="8908d-125">В следующем примере показано, как генерировать метаданные для реализации и конфигурации простой службы.</span><span class="sxs-lookup"><span data-stu-id="8908d-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="8908d-126">Экспорт метаданных в контракт службы.</span><span class="sxs-lookup"><span data-stu-id="8908d-126">To export metadata for the service contract.</span></span>  
  
```  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="8908d-127">Экспорт метаданных в контракты данных.</span><span class="sxs-lookup"><span data-stu-id="8908d-127">To export metadata for the data contracts.</span></span>  
  
```  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="8908d-128">Экспорт метаданных в реализацию службы.</span><span class="sxs-lookup"><span data-stu-id="8908d-128">To export metadata for the service implementation.</span></span>  
  
```  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="8908d-129">`<path>` является путем к файлу Contracts.dll.</span><span class="sxs-lookup"><span data-stu-id="8908d-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8908d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8908d-130">See Also</span></span>  
 [<span data-ttu-id="8908d-131">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="8908d-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="8908d-132">Экспорт и импорт метаданных</span><span class="sxs-lookup"><span data-stu-id="8908d-132">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
