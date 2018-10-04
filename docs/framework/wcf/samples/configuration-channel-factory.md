---
title: Производство канала настройки
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: b5dbabf8cdc28cc2beaf343b0377528c6ced1c66
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778592"
---
# <a name="configuration-channel-factory"></a>Производство канала настройки
В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> Обеспечивает возможность централизованного управления настройки клиента WCF. Это также можно использовать в случаях, когда конфигурация выбирается или изменяется после времени загрузки домена приложения.

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

1.  Откройте Visual Studio 2012 с правами администратора.

2.  Щелкните правой кнопкой мыши решение ConfigurationChannelFactory (2 проекта), а затем выберите **свойства**.

3.  В **общие свойства**выберите **запускаемым проектом**, а затем нажмите кнопку **несколько запускаемых проектов**.

4.  Переместить **службы** проекта в начале списка, с помощью **действие «Start»** и переместите **клиента** проекта после **службы**проекта, а также с **действие «Start»**, поэтому **клиента** проекта выполняется после **службы** проекта.

5.  Нажмите кнопку **ОК**, а затем нажмите клавишу F5 (или сочетание клавиш CTRL + F5), чтобы запустить образец.

> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
