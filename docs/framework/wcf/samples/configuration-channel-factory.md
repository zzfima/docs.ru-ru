---
title: "Производство канала настройки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a79a5c4997403f018ba34aea65e4c9fadab29443
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-channel-factory"></a>Производство канала настройки
В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> обеспечивает возможность централизованного управления конфигурацией клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Это также можно использовать в случаях, когда конфигурация выбирается или изменяется после времени загрузки домена приложения.  
  
## <a name="demonstrates"></a>Демонстрации  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a>Обсуждение  
 В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> для добавления определенного файла конфигурации к клиентскому приложению без использования файла конфигурации приложения по умолчанию.  
  
 Образец состоит из двух проектов. Первый проект представляет собой простую службу, запускаемую в ответ на сообщения, передаваемые от клиентов. Второй проект - это клиентское приложение, которое создает два объекта <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> с использованием <xref:System.Configuration.ExeConfigurationFileMap> для файла конфигурации Test.config и использует их для взаимодействия со службой. Оба клиента взаимодействуют со службой с использованием конфигурации, указанной в Test.config.  
  
 В следующем коде к клиентскому приложению добавляется пользовательский файл конфигурации.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с правами администратора.  
  
2.  Щелкните правой кнопкой мыши решение ConfigurationChannelFactory (2 проекта), а затем выберите **свойства**.  
  
3.  В **общие свойства**выберите **запускаемый проект**, а затем нажмите кнопку **несколько запускаемых проектов**.  
  
4.  Переместить **службы** проекта, в начале списка, с **«Start» действие**и переместите **клиента** проекта после **службы**проекта, также с **«Start» действие**, поэтому **клиента** проекта выполняется после **службы** проекта.  
  
5.  Нажмите кнопку **ОК**, а затем нажмите клавишу F5 (или сочетание клавиш CTRL + F5), чтобы запустить образец.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
