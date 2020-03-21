---
title: Проверка безопасности
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: 17e6e250c6b345477f7c9b377eb8e16ff4331ca7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183372"
---
# <a name="security-validation"></a>Проверка безопасности
Этот образец показывает, как с помощью пользовательского поведения проверять службы на компьютере на соответствие определенным условиям. В этом образце службы проверяются с помощью пользовательского поведения путем сканирования каждой конечной точки службы и проверки, содержат ли они безопасные элементы привязки. Этот пример основан на [получении начала](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="endpoint-validation-custom-behavior"></a>Пользовательское поведение проверки конечной точки  
 Добавив код пользователя в метод `Validate`, содержащийся в интерфейсе <xref:System.ServiceModel.Description.IServiceBehavior>, для службы или конечной точки можно создать пользовательское поведение, позволяющее выполнять определенные пользователем действия. Следующий код служит для перебора в цикле всех конечных точек, содержащихся в службе, и поиска безопасных привязок в коллекциях привязок конечных точек.  
  
```csharp
public void Validate(ServiceDescription serviceDescription,
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any
        // secure binding elements. Transport, Asymmetric, and Symmetric
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 При добавлении приведенного ниже кода в файл Web.config добавляется расширение поведения `serviceValidate` для распознавания службой.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 После того как расширение поведения добавлено в службу, можно добавить поведение `endpointValidate` в список поведений в файле Web.config и, таким образом, в службу.  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 Поведения и их расширения, добавленные в файл Web.config, применяют поведение к отдельным службам, а при добавлении в файл Machine.config поведение применяется ко всем службам, работающим на компьютере.  
  
> [!NOTE]
> При добавлении поведения во все службы предлагается перед внесением каких-либо изменений в файл Machine.config создать резервную копию этого файла.  
  
 Теперь запустите клиент, содержащийся в каталоге client\bin данного образца. Исключение происходит со следующим сообщением: "Запрошеннаяhttp://localhost/servicemodelsamples/service.svcслужба" не может быть активирована. Это ожидаемая ситуация, так как поведение проверки конечной точки считает конечную точку небезопасной и запрещает запуск службы. Поведение также создает внутреннее исключение, которое описывает, какая конечная точка является небезопасной, и записывает сообщение в системную программу Просмотр событий, в раздел источника "System.ServiceModel 4.0.0.0", категория "WebHost". В данном образце можно также включить трассировку в службе. Это позволит конечному пользователю просматривать исключения, созданные поведением проверки конечных точек, открыв трассировки службы с помощью программы Service Trace Viewer.  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a>Просмотр сообщений исключения сбоя проверки конечной точки в программе Просмотр событий  
  
1. Нажмите меню **«Пуск»** и выберите **«Бег»...**  
  
2. Введите `eventvwr` и нажмите кнопку **ОК**.  
  
3. В окне просмотра событий нажмите **приложение**.  
  
4. Дважды щелкните недавно добавленное событие "System.ServiceModel 4.0.0.0" в категории "WebHost" в окне **приложения** для просмотра небезопасных сообщений конечных точек.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a>См. также раздел

- [Образцы наблюдения за AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
