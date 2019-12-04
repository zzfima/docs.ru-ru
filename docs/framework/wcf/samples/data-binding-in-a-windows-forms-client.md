---
title: Привязка данных в клиенте Windows Forms
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: 70bb47ff13e639bd34ad4df2f5aa6f09fb00b41d
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716383"
---
# <a name="data-binding-in-a-windows-forms-client"></a>Привязка данных в клиенте Windows Forms
В этом образце показано, как выполнить привязку к данным, возвращаемым службой Windows Communication Foundation (WCF) в приложении Windows Forms.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Пример состоит из клиентского Windows Forms приложения (exe) и службы WCF, размещенной в службы IIS (IIS).  
  
 Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`. Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 Привязка данных выполняется на стороне клиента в приложении Windows Forms. `DataGridView` определяется в конструкторе Windows Forms, который является графическим представлением данных. Кроме того, создается посредник с именем `BindingSource`. Источник данных `BindingSource` имеет значение массива данных, возвращаемых службой. Предназначение источника данных `BindingSource` заключается в предоставлении уровня косвенного обращения между данными и представлением данных. Все взаимодействие с данными, такое как перемещение, сортировка, фильтрация и обновление, осуществляется посредством вызовов компонента `BindingSource`. Чтобы выполнить привязку данных к `DataGridView`, источнику данных `datasource` объекта `DataGridView` присваивается значение объекта `BindingSource`. Все данные, возвращаемые из службы WCF, затем отображаются в графическом виде для пользователя.  Каждый раз, когда пользователь нажимает кнопку, возвращаемые данные автоматически обновляются в объекте `DataGridView`, который использует привязку данных.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
