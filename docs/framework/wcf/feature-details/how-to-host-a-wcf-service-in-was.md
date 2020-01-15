---
title: Практическое руководство. Размещение службы WCF в WAS
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 9945e398bbd33776cce808b44388a4415da297a1
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964770"
---
# <a name="how-to-host-a-wcf-service-in-was"></a>Практическое руководство. Размещение службы WCF в WAS
В этом разделе описаны основные шаги, необходимые для создания службы активации процессов Windows (также известной как WAS), размещенной Windows Communication Foundation служб (WCF). WAS является службой активации нового процесса, представляющей собой обобщение возможностей Internet Information Services (IIS), которые работают с транспортными протоколами, отличными от HTTP. WCF использует интерфейс адаптера прослушивателя для передачи запросов на активацию, полученных через протоколы, отличные от HTTP, которые поддерживаются WCF, такие как TCP, именованные каналы и очередь сообщений.  
  
 Данный параметр размещения требует правильно установленных и настроенных компонентов активации WAS, но не требует написания кода размещения как части приложения. Дополнительные сведения об установке и настройке см. в разделе [как установить и настроить компоненты активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
> [!WARNING]
> Активация WAS не поддерживается, если канал обработки запросов веб-сервера работает в классическом режиме. Чтобы использовать активацию WAS, канал обработки запросов веб-сервера необходимо перевести в интегрированный режим.  
  
 Если служба WCF размещена в WAS, стандартные привязки используются обычным способом. Однако при использовании <xref:System.ServiceModel.NetTcpBinding> и <xref:System.ServiceModel.NetNamedPipeBinding> для настройки служб, размещенных на WAS, ограничение должно быть удовлетворено. Если разные конечные точки используют один и тот же транспорт, параметры привязки должны соответствовать семи следующим свойствам:  
  
- ConnectionBufferSize  
  
- ChannelInitializationTimeout  
  
- MaxPendingConnections  
  
- MaxOutputDelay  
  
- MaxPendingAccepts  
  
- ConnectionPoolSettings.IdleTimeout  
  
- ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint  
  
 В противном случае, конечная точка, запущенная первой, всегда определяет значения этих параметров, а добавленные позже конечные точки, если они не совпадают с этими настройками, вызывают <xref:System.ServiceModel.ServiceActivationException>.  
  
 Исходный экземпляр этого примера см. в разделе [Активация TCP](../../../../docs/framework/wcf/samples/tcp-activation.md).  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a>Создание базовой службы, размещенной на WAS  
  
1. Определите контракт службы для данного типа службы.  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2. Реализуйте контракт службы в классе службы. Обратите внимание, что информация об адресе или привязке не указывается внутри реализации службы. Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3. Создайте файл Web.config, чтобы определить привязку <xref:System.ServiceModel.NetTcpBinding> для использования конечными точками `CalculatorService`.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <bindings>  
          <netTcpBinding>  
            <binding portSharingEnabled="true">  
              <security mode="None" />  
            </binding>  
          </netTcpBinding>  
        </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. Создайте файл Service.svc, содержащий следующий код.  
  
   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```
  
5. Разместите файл Service.svc в виртуальном каталоге своего IIS.  
  
### <a name="to-create-a-client-to-use-the-service"></a>Создание клиента для использования службы  
  
1. Используйте [служебную программу метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.  
  
    ```console
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание, что информация об адресе и привязке нигде внутри реализации службы не указывается. Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4. Конфигурация для клиента, использующего <xref:System.ServiceModel.NetTcpBinding>, также создается программой Svcutil.exe. Имя этого файла должно задаваться в файле App.config, если используется Visual Studio.  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]   
  
5. Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6. Скомпилируйте и запустите клиент.  
  
## <a name="see-also"></a>См. также:

- [Активация TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
