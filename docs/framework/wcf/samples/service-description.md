---
title: Описание службы
ms.date: 03/30/2017
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
ms.openlocfilehash: d86a6a78995042f0c6a45cf6e40e31c3e515e8eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="service-description"></a>Описание службы
Образец "Описание службы" показывает, как служба может получать свое описание службы в среде выполнения. Пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), с дополнительную операцию службы возвращать описательные сведения о службе. Возвращаемые сведения содержат базовые адреса и конечные точки службы. Служба предоставляет эти сведения с помощью классов <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> и <xref:System.ServiceModel.Description.ServiceDescription>.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец содержит модифицированную версию контракта калькулятора под названием `IServiceDescriptionCalculator`. Контракт определяет дополнительную операцию службы с именем `GetServiceDescriptionInfo`, возвращающую клиенту многострочный текст, описывающий базовый адрес или адреса и конечную точку или точки службы.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 Код реализации операции `GetServiceDescriptionInfo` использует класс <xref:System.ServiceModel.Description.ServiceDescription> для перечисления конечных точек службы. Так как у конечных точек службы могут быть относительные адреса, он сначала перечисляет базовые адреса службы. Чтобы вернуть все эти сведения, код получает контекст операции с помощью <xref:System.ServiceModel.OperationContext.Current%2A>. Класс <xref:System.ServiceModel.ServiceHost> и его объект <xref:System.ServiceModel.Description.ServiceDescription> извлекаются из контекста операции. Чтобы перечислить конечные точки службы, код выполняет итерацию коллекции <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> узла службы. Чтобы перечислить служебные конечные точки службы, код выполняет итерацию коллекции конечных точек описания службы.  
  
```  
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 При выполнении образца видны операции калькулятора и сведения службы, возвращаемые операцией `GetServiceDescriptionInfo`. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
  
## <a name="see-also"></a>См. также
