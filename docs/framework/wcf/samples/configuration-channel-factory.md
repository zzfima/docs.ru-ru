---
title: "Производство канала настройки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Производство канала настройки
В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> обеспечивает возможность централизованного управления конфигурацией клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Это также можно использовать в случаях, когда конфигурация выбирается или изменяется после времени загрузки домена приложения.  
  
## Демонстрации  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## Обсуждение  
 В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> для добавления определенного файла конфигурации к клиентскому приложению без использования файла конфигурации приложения по умолчанию.  
  
 Образец состоит из двух проектов.Первый проект представляет собой простую службу, запускаемую в ответ на сообщения, передаваемые от клиентов.Второй проект — это клиентское приложение, которое создает два объекта <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> с использованием <xref:System.Configuration.ExeConfigurationFileMap> для файла конфигурации Test.config и использует их для взаимодействия со службой.Оба клиента взаимодействуют со службой с использованием конфигурации, указанной в Test.config.  
  
 В следующем коде к клиентскому приложению добавляется пользовательский файл конфигурации.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
  
```  
  
#### Настройка, построение и выполнение образца  
  
1.  Откройте среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с правами администратора.  
  
2.  Щелкните правой кнопкой мыши решение ConfigurationChannelFactory \(2 проекта\) и выберите **Свойства**.  
  
3.  В разделе **Общие свойства** выберите **Запускаемый проект**, затем **Несколько запускаемых проектов**.  
  
4.  Переместите проект **Служба** в начало списка с помощью **Действие «Пуск»**, а затем поместите проект **Клиент** после проекта **Служба**, также с помощью **Действие «Пуск»**, чтобы проект **Клиент** был запущен после проекта **Служба**.  
  
5.  Нажмите кнопку **ОК**, а затем клавишу F5 \(или CTRL\+F5\) для выполнения образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`