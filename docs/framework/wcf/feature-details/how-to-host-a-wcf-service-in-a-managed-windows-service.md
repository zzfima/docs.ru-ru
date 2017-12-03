---
title: "Практическое руководство. Размещение службы WCF в управляемой службе Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e8572541e0bf9ddcfb93939c177b5cb8c440b41
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Практическое руководство. Размещение службы WCF в управляемой службе Windows
В этом разделе описаны основные шаги по созданию службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], размещенной в службе Windows. Сценарий реализуется с помощью возможности размещения в управляемой службе Windows и представляет собой работающую в течение продолжительного времени службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенную за пределами служб IIS в защищенной среде, которая не активируется сообщениями. Вместо этого время существования службы контролируется операционной системой. Данный вариант размещения доступен во всех версиях Windows.  
  
 Службами Windows можно управлять при помощи Microsoft.ManagementConsole.SnapIn в консоли управления (MMC) и можно настроить их автоматический запуск при загрузке системы. Возможность размещения состоит из регистрации домена приложения, где служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] размещена как управляемая служба Windows, так что время существования процесса службы контролируется диспетчером служб для служб Windows.  
  
 Код службы включает в себя реализацию службы контракта службы, класс службы Windows и класс установщика. Класс реализации службы, `CalculatorService`, является службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Класс `CalculatorWindowsService` является службой Windows. Чтобы считаться службой Windows, этот класс наследует от класса `ServiceBase` и реализует методы `OnStart` и `OnStop`. В методе `OnStart` создается объект <xref:System.ServiceModel.ServiceHost> для типа `CalculatorService` и открывается. В методе `OnStop` служба останавливается и освобождается. Основное приложение также отвечает за предоставление базового адреса для узла службы, настроенного в параметрах приложения. Класс установщика, унаследованный от класса <xref:System.Configuration.Install.Installer>, позволяет выполнить установку программы как службы Windows с помощью Installutil.exe.  
  
### <a name="construct-the-service-and-provide-the-hosting-code"></a>Создание службы и предоставление кода размещения  
  
1.  Создайте новый проект консольного приложения Visual Studio с именем Service.  
  
2.  Измените имя файла Program.cs на Service.cs.  
  
3.  Измените пространство имен на Microsoft.ServiceModel.Samples.  
  
4.  Добавьте ссылки на следующие сборки.  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceProcess.dll  
  
    -   System.Configuration.Install.dll  
  
5.  Добавьте следующие операторы using в файл Service.cs.  
  
     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]  
  
6.  Определите контракт службы `ICalculator`, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]  
  
7.  Реализуйте контракт службы в классе с именем `CalculatorService`, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]  
  
8.  Создайте новый класс с именем `CalculatorWindowsService`, производный от класса <xref:System.ServiceProcess.ServiceBase>. Добавьте локальную переменную с именем `serviceHost`, чтобы создать ссылку на экземпляр <xref:System.ServiceModel.ServiceHost>. Определите метод `Main`, который вызывает `ServiceBase.Run(new CalculatorWindowsService)`.  
  
     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]  
  
9. Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, создав и открыв новый экземпляр <xref:System.ServiceModel.ServiceHost>, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]  
  
10. Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A>, закрывающий <xref:System.ServiceModel.ServiceHost>, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]  
  
11. Создайте новый класс с именем `ProjectInstaller`, производный от <xref:System.Configuration.Install.Installer> и помеченный атрибутом <xref:System.ComponentModel.RunInstallerAttribute>, установленным в значение `true`. Это позволяет устанавливать службу Windows программой Installutil.exe.  
  
     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]  
  
12. Удалите класс `Service`, созданный при создании проекта.  
  
13. Добавьте в проект файл конфигурации приложения. Замените содержимое этого файла следующим XML-кодом конфигурации.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>    <services>  
          <!-- This section is optional with the new configuration model  
               introduced in .NET Framework 4. -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                   behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceMetadata httpGetEnabled="true"/>  
              <serviceDebug includeExceptionDetailInFaults="False"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Щелкните правой кнопкой мыши файл App.config в **обозревателе решений** и выберите **свойства**. В разделе **Копировать в выходной каталог** выберите **копировать, если новее**.  
  
     В этом примере конечные точки явно задаются в файле конфигурации. Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию. В этом примере, поскольку для службы параметр <xref:System.ServiceModel.Description.ServiceMetadataBehavior> установлен в значение `true`, в ней также будет включена публикация метаданных. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]см. по умолчанию конечные точки, привязки и поведения, [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
### <a name="install-and-run-the-service"></a>Установка и запуск службы  
  
1.  Постройте решение, чтобы создать исполняемый файл `Service.exe`.  
  
2.  Откройте командную строку [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и перейдите в каталог проекта. В командной строке введите `installutil bin\service.exe`, чтобы установить службу Windows.  
  
    > [!NOTE]
    >  Если командная строка [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] не используется, убедитесь, что каталог `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` входит в системный путь.  
  
     В командной строке введите `services.msc`, чтобы получить доступ к диспетчеру служб. Служба Windows должна появиться в списке служб с именем WCFWindowsServiceSample. Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может отвечать клиентам, только если запущена служба Windows. Чтобы запустить службу, щелкните его правой кнопкой в диспетчер управления Службами и выберите «Пуск» или тип **команда net start WCFWindowsServiceSample** в командной строке.  
  
3.  Чтобы внести изменения в службу, необходимо предварительно остановить ее и удалить. Чтобы остановить службу, щелкните правой кнопкой мыши в Диспетчере служб и выберите «Остановить», или **типа net stop WCFWindowsServiceSample** в командной строке. Учтите, что если остановить службу Windows, а затем запустить клиент, то когда клиент попытается обратиться к службе, будет вызвано исключение <xref:System.ServiceModel.EndpointNotFoundException>. Удаление типа службы Windows **installutil /u bin\service.exe** в командной строке.  
  
## <a name="example"></a>Пример  
 Код, используемый в этом разделе, полностью приведен ниже.  
  
 [!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
 [!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]  
  
 Как и в случае резидентного размещения, среда размещения службы Windows требует, чтобы код размещения являлся частью приложения. Служба реализуется как консольное приложение и содержит собственный код размещения. В других средах размещения, таких как служба активации Windows (WAS), размещающих в IIS, писать код размещения необязательно.  
  
## <a name="see-also"></a>См. также  
 [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md)  
 [Размещение в управляемом приложении](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 [Размещение служб](../../../../docs/framework/wcf/hosting-services.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
