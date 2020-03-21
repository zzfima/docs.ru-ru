---
title: Привязка данных в клиенте Windows Forms
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: d538e8a525f8d07e9ac9f57d4b10119907602d90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145050"
---
# <a name="data-binding-in-a-windows-forms-client"></a>Привязка данных в клиенте Windows Forms
В этом примере показано, как связываться с данными, возвращенными службой Windows Communication Foundation (WCF) в приложении Windows Forms.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Выборка состоит из клиентских приложений Windows Forms (.exe) и сервиса WCF, размещенного службой интернет-информации (IIS).  
  
 Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`. Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 Привязка данных выполняется на стороне клиента в приложении Windows Forms. `DataGridView` определяется в конструкторе Windows Forms, который является графическим представлением данных. Кроме того, создается посредник с именем `BindingSource`. Источник данных `BindingSource` имеет значение массива данных, возвращаемых службой. Предназначение источника данных `BindingSource` заключается в предоставлении уровня косвенного обращения между данными и представлением данных. Все взаимодействие с данными, такое как перемещение, сортировка, фильтрация и обновление, осуществляется посредством вызовов компонента `BindingSource`. Чтобы выполнить привязку данных к `DataGridView`, источнику данных `datasource` объекта `DataGridView` присваивается значение объекта `BindingSource`. Все данные, возвращенные из службы WCF, затем графически отображаются пользователю.  Каждый раз, когда пользователь нажимает кнопку, возвращаемые данные автоматически обновляются в объекте `DataGridView`, который использует привязку данных.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
