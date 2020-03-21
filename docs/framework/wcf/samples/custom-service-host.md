---
title: Пользовательский узел службы
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 2aed557d1d045c08aed206660aa7b4b75ffe0e2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145076"
---
# <a name="custom-service-host"></a>Пользовательский узел службы
Этот образец показывает, как применять пользовательский производный класс для класса <xref:System.ServiceModel.ServiceHost>, чтобы изменять поведение службы во время выполнения. Такой подход обеспечивает поддерживающую повторное использование альтернативу настройке большого числа служб одинаковым образом. Кроме того, в этом примере демонстрируется, как с помощью класса <xref:System.ServiceModel.Activation.ServiceHostFactory> применять пользовательский объект ServiceHost в среде размещения IIS или службы активации Windows (WAS).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>Сценарий
 Для предотвращения непреднамеренного раскрытия потенциально чувствительных метаданных службы конфигурация Windows Communication Foundation (WCF) отскакивает к публикации метаданных. Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации.  
  
 Включение публикации метаданных для большого числа служб связано с добавлением одинаковых элементов конфигурации для всех служб по отдельности, что приводит к появлению значительного объема повторяющейся информации конфигураций. Вместо конфигурации всех служб по отдельности можно написать принудительный код, один раз включающий публикацию метаданных, а затем использовать его повторно для нескольких других служб. Для этого создается новый класс, наследуемый от класса <xref:System.ServiceModel.ServiceHost>, переопределяющий метод `ApplyConfiguration`() так, чтобы принудительно добавить поведение публикации метаданных.  
  
> [!IMPORTANT]
> Для ясности этот образец демонстрирует создание незащищенной конечной точки публикации метаданных. Такие конечные точки являются потенциально доступными для анонимных не прошедших проверку подлинности потребителей, поэтому перед развертыванием таких конечных точек следует соблюдать осторожность и убедиться, что публичное раскрытие метаданных службы уместно.  
  
## <a name="implementing-a-custom-servicehost"></a>Реализация пользовательского ServiceHost
 Класс <xref:System.ServiceModel.ServiceHost> предоставляет несколько полезных виртуальных методов, которые наследующие классы могут переопределять, чтобы изменять поведение службы во время выполнения. Например, метод `ApplyConfiguration`() выполняет чтение сведений конфигурации службы из хранилища конфигураций и соответствующим образом изменяет объект <xref:System.ServiceModel.Description.ServiceDescription> ведущего приложения. Реализация по умолчанию считывает конфигурацию из файла конфигурации приложения. Пользовательские реализации могут переопределять метод `ApplyConfiguration`() для дополнительного изменения<xref:System.ServiceModel.Description.ServiceDescription> с помощью императивного кода или даже полностью заменять хранилище конфигураций по умолчанию. Например, чтобы читать конфигурацию конечной точки службы не из файла конфигурации приложения, а из базы данных.  
  
 В этом примере нам нужно построить пользовательский класс ServiceHost, добавляющий поведение ServiceMetadataBehavior (включающее публикацию метаданных), даже если такое поведение не добавлено в файл конфигурации службы явно. Для этого нужно создать новый класс, наследуемый от класса <xref:System.ServiceModel.ServiceHost>, переопределяющий метод `ApplyConfiguration`().  
  
```csharp
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to
    //alter the ServiceDescription prior to opening  
    //the service host.
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 Так как игнорировать конфигурацию, предоставленную в файле конфигурации приложения, не нужно, переопределение `ApplyConfiguration`() в первую очередь вызывает базовую реализацию. После выполнения этого метода можно принудительно добавить в описание поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior> с помощью следующего принудительного кода.  
  
```csharp
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,
    //so we do not have any work to do.  
    return;  
}  
```  
  
 Наконец, переопределение `ApplyConfiguration`() должно добавить конечную точку метаданных по умолчанию. По соглашению для каждого универсального кода ресурса (URI) в коллекции BaseAddresses главного приложения службы создается по одной конечной точке метаданных.  
  
```csharp
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a>Использование пользовательского ServiceHost в резидентной службе  
 Выполненную реализацию пользовательского ServiceHost можно использовать для добавления поведения публикации метаданных к любой службе, разместив эту службу внутри экземпляра `SelfDescribingServiceHost`. В следующем примере кода демонстрируется его использование с резидентной службой.  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 Пользовательское ведущее приложение продолжает считывать конфигурацию конечной точки службы из файла конфигурации приложения, как если бы для размещения службы использовался класс <xref:System.ServiceModel.ServiceHost> по умолчанию. Но так как в пользовательское основное приложение добавлена логика, включающая публикацию метаданных, нет необходимости явно включать поведение публикации метаданных в конфигурации. Этот подход удобен при создании приложения, содержащего несколько служб, для которых нужно включить публикацию метаданных. Он позволяет не повторять несколько раз запись одинаковых элементов конфигурации.  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a>Использование пользовательского ServiceHost в службах IIS или WAS  
 Использовать пользовательский узел службы в резидентных сценариях нетрудно, потому что за создание и открытие экземпляра основного приложения службы отвечает в итоге код вашего приложения. Однако в среде хостинга IIS или WAS инфраструктура WCF динамически мгновенно принимает универсал службы в ответ на входящие сообщения. В этой среде размещения также можно использовать пользовательские узлы служб, но для этого требуется дополнительный код в виде ServiceHostFactory. В следующем коде приведен класс, наследуемый от <xref:System.ServiceModel.Activation.ServiceHostFactory>, возвращающий экземпляры пользовательского `SelfDescribingServiceHost`.  
  
```csharp
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,
                                             baseAddresses);  
    }  
}  
```  
  
 Реализация пользовательской фабрики ServiceHostFactory тоже вполне очевидна. Вся пользовательская логика находится внутри реализации ServiceHost; фабрика возвращает экземпляр производного класса.  
  
 Для использования пользовательской фабрики с реализацией службы необходимо добавить в файл SVC службы дополнительные метаданные.  
  
```xml
<%@ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 В директиву `Factory` добавлен дополнительный атрибут `@ServiceHost`, в качестве значения которого передано имя типа CLR пользовательской фабрики. Когда IIS или WAS получает сообщение для этой службы, инфраструктура хостинга WCF сначала создает экземпляр ServiceHostFactory, а затем мгновенно вызывает сам ухож службы, позвонив. `ServiceHostFactory.CreateServiceHost()`  
  
## <a name="running-the-sample"></a>Выполнение примера  
 В этом примере содержатся полностью функциональные реализации клиента и службы, но цель этого примера — продемонстрировать изменение поведения службы во время выполнения с помощью пользовательского ведущего приложения, выполните следующие действия.  
  
### <a name="observe-the-effect-of-the-custom-host"></a>Обратите внимание на влияние пользовательского хоста
  
1. Откройте файл Web.config службы и заметьте, что нет конфигурации, явно позволяющей метаданным для службы.  
  
2. Откройте файл .svc службы и @ServiceHost заметьте, что его директива содержит атрибут Factory, который определяет название пользовательского ServiceHostFactory.  
  
### <a name="set-up-build-and-run-the-sample"></a>Настройка, создание и запуск образца
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](one-time-setup-procedure-for-the-wcf-samples.md)

2. Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](building-the-samples.md)

3. После того, как решение было построено, запустите Setup.bat для настройки приложения ServiceModelSamples в IIS 7.0. Каталог ServiceModelSamples теперь должен отображаться как приложение IIS 7.0.

4. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](running-the-samples.md)

5. Чтобы удалить приложение IIS 7.0, запустите *Cleanup.bat*.

## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Размещение службы WCF в IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
