---
title: Производство канала настройки
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 1b74c15599ebc932a2a0ed46d646b54bec986794
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045646"
---
# <a name="configuration-channel-factory"></a>Производство канала настройки
В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> Позволяет централизованно управлять конфигурацией клиента WCF. Это также можно использовать в случаях, когда конфигурация выбирается или изменяется после времени загрузки домена приложения.

## <a name="demonstrates"></a>Демонстрации
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>Обсуждение
 В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> для добавления определенного файла конфигурации к клиентскому приложению без использования файла конфигурации приложения по умолчанию.

 Образец состоит из двух проектов. Первый проект представляет собой простую службу, запускаемую в ответ на сообщения, передаваемые от клиентов. Второй проект - это клиентское приложение, которое создает два объекта <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> с использованием <xref:System.Configuration.ExeConfigurationFileMap> для файла конфигурации Test.config и использует их для взаимодействия со службой. Оба клиента взаимодействуют со службой с использованием конфигурации, указанной в Test.config.

 В следующем коде к клиентскому приложению добавляется пользовательский файл конфигурации.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Откройте Visual Studio 2012 с правами администратора.

2. Щелкните правой кнопкой мыши решение Конфигуратиончаннелфактори (2 проекта) и выберите пункт **Свойства**.

3. В окне **Общие свойства**выберите **запускаемый проект**и щелкните **Несколько запускаемых проектов**.

4. Переместите проект **службы** в начало списка с **действием "Запуск"** , а затем переместите проект **клиента** после проекта **службы** , а также с **действием "Запуск"** , чтобы выполнить **клиентский** проект. после проекта **службы** .

5. Нажмите кнопку **ОК**, а затем клавишу F5 (или CTRL + F5), чтобы запустить пример.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
