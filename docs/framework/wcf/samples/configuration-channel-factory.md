---
title: Производство канала настройки
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 0f00ba5e217420fe416100071d380e413c3df118
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183951"
---
# <a name="configuration-channel-factory"></a>Производство канала настройки
В образце описывается использование <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. Позволяет <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> централизованное управление конфигурацией клиентов WCF. Это также можно использовать в случаях, когда конфигурация выбирается или изменяется после времени загрузки домена приложения.

## <a name="demonstrates"></a>Что демонстрирует
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

1. Open Visual Studio 2012 с привилегиями администратора.

2. Нажмите правой кнопкой мыши на решение ConfigurationChannelFactory (2 проекта), а затем выберите **Свойства.**

3. В **общие свойства**, выберите запуск **проекта**, а затем нажмите **Несколько проектов запуска**.

4. Переместите проект **Службы** в начало списка, с **действием «Старт»,** а затем переместите проект **Клиента** после проекта **Службы,** также с **помощью акции «Старт»,** так что проект **Клиента** выполняется после проекта **Service.**

5. Нажмите **OK**, а затем нажмите F5 (или CTRL-F5), чтобы запустить образец.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
