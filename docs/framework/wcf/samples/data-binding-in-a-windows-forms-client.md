---
title: Привязка данных в клиенте Windows Forms
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: a84aeedba89cc7a5c267a0fd1f6c4f604fe80d43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-binding-in-a-windows-forms-client"></a>Привязка данных в клиенте Windows Forms
В этом примере показано, как выполнить привязку данных, возвращенных службой Windows Communication Foundation (WCF), в приложении Windows Forms.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Этот образец состоит из приложения Windows Forms клиента (EXE) и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенной в службах IIS.  
  
 Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`. Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 Привязка данных выполняется на стороне клиента в приложении Windows Forms. `DataGridView` определяется в конструкторе Windows Forms, который является графическим представлением данных. Кроме того, создается посредник с именем `BindingSource`. Источник данных `BindingSource` имеет значение массива данных, возвращаемых службой. Предназначение источника данных `BindingSource` заключается в предоставлении уровня косвенного обращения между данными и представлением данных. Все взаимодействие с данными, такое как перемещение, сортировка, фильтрация и обновление, осуществляется посредством вызовов компонента `BindingSource`. Чтобы выполнить привязку данных к `DataGridView`, источнику данных `datasource` объекта `DataGridView` присваивается значение объекта `BindingSource`. Все данные, возвращаемые службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], представляются пользователю в графическом виде.  Каждый раз, когда пользователь нажимает кнопку, возвращаемые данные автоматически обновляются в объекте `DataGridView`, который использует привязку данных.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a>См. также
