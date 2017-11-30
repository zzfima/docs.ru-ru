---
title: "Привязка данных в клиенте Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 163bd72d9c42680d72c435e8266c75876490a2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a>Привязка данных в клиенте Windows Forms
В этом примере показано, как выполнить привязку к данным, возвращаемым службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в приложении Windows Forms.  
  
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
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a>См. также
