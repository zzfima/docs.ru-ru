---
title: "Активация на основе конфигурации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Активация на основе конфигурации
В этом образце показывается способ активации служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] без использования SVC\-файла.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## Подробные сведения об образце  
 В этом образце клиентом является тестовый клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а служба размещается в службах IIS.  
  
> [!NOTE]
>  Инструкции по настройке и построению этого образца приведены в конце этого раздела.  
  
### Активация служб без использования SVC\-файла  
 В [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] для активации служб необходим SVC\-файл.Это привело к появлению дополнительных затрат на управление, поскольку требовалось выполнить развертывание дополнительного файла, который необходимо поддерживать вместе с приложением.В выпуске [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] компоненты активации можно настроить с помощью файла конфигурации приложения.  
  
 В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] реализован новый элемент конфигурации \(<xref:System.ServiceModel.Configuration.ServiceActivationElement>\) в разделе <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> файла конфигурации приложения.Коллекция <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> принимает коллекцию служб для активации, как показано в предыдущем примере кода.  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
  
```  
  
 Необходимо отметить, что конфигурация схожа с конфигурацией SVC\-файлов.Также реализуется дополнительный атрибут `relativeAddress`, предоставляющий адрес службы.Относительный адрес также является виртуальным путем службы.Узел извлекает файл Web.config из файла в местоположении `virtualPath` \(если имеется\), в противном случае узел выполняет рекурсивный поиск родительской папки.  
  
> [!NOTE]
>  Для работы этого образца требуется размещение в службах IIS.  
  
#### Использование этого образца  
  
1.  Используйте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], чтобы открыть файл Service.csproj.  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Проверьте службу, запустив WCFTestClient.exe.  
  
4.  В [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] перейдите в папку %SystemDrive%\\Program Files\\Microsoft Visual Studio 10.0\\Common7\\IDE.  
  
5.  Запустите файл WcfTestClient.exe.  
  
6.  Задайте адрес MEX службы.  
  
7.  Нажмите CTRL\+SHIFT\+A, чтобы задать адрес службы.  
  
8.  Задайте адрес http:\/\/localhost\/ServiceModelSamples\/Calculator.svc.  
  
9. Выполните операцию `Add`.Задайте для параметра `n1` значение, равное 10, а для параметра `n2` значение, равное 15.  
  
10. Нажмите **Вызвать**.  
  
     Ожидаемым результатом является 25.  
  
#### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  После построения решения запустите файл Setup.bat, чтобы настроить приложение ServiceModelSamples в службах IIS.Теперь каталог ServiceModelSamples должен представляться как приложение IIS.  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также  
 [Образцы размещения и сохраняемости AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)