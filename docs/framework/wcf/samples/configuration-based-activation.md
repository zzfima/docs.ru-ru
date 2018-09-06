---
title: Активация на основе конфигурации
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: e016dffdaf93b222c1fd2380bfa175256b009068
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43742320"
---
# <a name="configuration-based-activation"></a>Активация на основе конфигурации
В этом примере показано, как активировать службы Windows Communication Foundation (WCF) без использования SVC-файла.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В этом образце клиентом является тестовый клиент WCF, а служба размещается в службах IIS.  
  
> [!NOTE]
>  Инструкции по настройке и построению этого образца приведены в конце этого раздела.  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a>Активация служб без использования SVC-файла  
 В [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] для активации служб необходим SVC-файл. Это привело к появлению дополнительных затрат на управление, поскольку требовалось выполнить развертывание дополнительного файла, который необходимо поддерживать вместе с приложением. В выпуске [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] компоненты активации можно настроить с помощью файла конфигурации приложения.  
  
 В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] реализован новый элемент конфигурации (<xref:System.ServiceModel.Configuration.ServiceActivationElement>) в разделе <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> файла конфигурации приложения. Коллекция <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> принимает коллекцию служб для активации, как показано в предыдущем примере кода.  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 Необходимо отметить, что конфигурация схожа с конфигурацией SVC-файлов. Также реализуется дополнительный атрибут `relativeAddress`, предоставляющий адрес службы. Относительный адрес также является виртуальным путем службы. Узел извлекает файл Web.config из файла в местоположении `virtualPath` (если имеется), в противном случае узел выполняет рекурсивный поиск родительской папки.  
  
> [!NOTE]
>  Для работы этого образца требуется размещение в службах IIS.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Используйте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], чтобы открыть файл Service.csproj.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Проверьте службу, запустив WCFTestClient.exe.  
  
4.  С помощью [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] найдите папку %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE.  
  
5.  Запустите файл WcfTestClient.exe.  
  
6.  Задайте адрес MEX службы.  
  
7.  Нажмите CTRL+SHIFT+A, чтобы задать адрес службы.  
  
8.  Задайте адрес http://localhost/ServiceModelSamples/Calculator.svc.  
  
9. Выполните операцию `Add`. Задайте для параметра `n1` значение, равное 10, а для параметра `n2` значение, равное 15.  
  
10. Нажмите клавишу **вызова**.  
  
     Ожидаемым результатом является 25.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  После построения решения запустите файл Setup.bat, чтобы настроить приложение ServiceModelSamples в службах IIS. Теперь каталог ServiceModelSamples должен представляться как приложение IIS.  
  
4.  Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также  
 [Образцы размещения AppFabric и сохраняемости](https://go.microsoft.com/fwlink/?LinkId=193961)
