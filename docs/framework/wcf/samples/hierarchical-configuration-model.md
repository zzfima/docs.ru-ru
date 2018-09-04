---
title: Иерархическая модель конфигурации
ms.date: 03/30/2017
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
ms.openlocfilehash: 8ca9b01eb022e2e2ab940866a6230e8227ceb2dc
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499345"
---
# <a name="hierarchical-configuration-model"></a>Иерархическая модель конфигурации
Этот образец демонстрирует реализацию иерархии файлов конфигурации для служб. Он также показывает то, как привязки, поведения служб и конечных точек наследуются с более высоких уровней иерархии.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Одна из функций, разработанных для WCF в [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] усовершенствование иерархической модели конфигурации. Примером модели иерархической конфигурации может служить модель, определенная файлом Machine.config -> Rootweb.config -> Web.config. В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] привязки и поведения, определенные на более высоких уровнях иерархии конфигурации, добавляются в службы без явной настройки. В этом образце показано, как можно упростить настройку служб с помощью элементов конфигурации, определенных на уровне компьютера или приложения.  
  
 В данном образце реализуется девять служб, которые распределяются по иерархии из трех уровней. В корне находится служба `Service1`. Службы `Service2` и `Service3` наследуют элементы по умолчанию от `Service1`. `Service4`, `Service5`, `Service6` и `Service7` определены на третьем уровне иерархии, наследуя элементы по умолчанию от `Service3`. Наконец, `Service10` и `Service11` находятся на четвертом уровне иерархии.  
  
 Все службы реализуют контракт `IDesc`. Далее приведено определение интерфейса `IDesc`, показывающее методы, доступ к которым имеется в этом интерфейсе. Интерфейс `IDesc` определен в файле Service1.cs.  
  
```csharp  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 Службы непосредственно реализуют эти методы. `ListEndpoints` проходит по всем конечным точкам службы и возвращает список всех конечных точек, которые имеет служба. `ListServiceBehaviors` проходит по всем поведениям, добавленным в службу, и возвращает список всех поведений службы, связанных с ней. `ListEndpointBehaviors` действует так же, как `ListServiceBehaviors`, но возвращает список поведений конечной точки.  
  
 Благодаря этой реализации клиент знает, сколько конечных точек имеет служба, а также какие поведения службы и конечной точки добавлены в службу. Клиент, реализованный как часть образца, добавляет ссылку на службу во все службы решения и показывает эти элементы для всех служб.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
#### <a name="to-run-the-client"></a>Запуск клиента  
  
1.  Откройте файл ConfigHierarchicalModel.sln с помощью [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Проект клиента еще не установлен в качестве запускаемого проекта; выполните следующие действия.  
  
    1.  В **обозревателе решений**, щелкните правой кнопкой мыши решение и выберите **свойства**.  
  
    2.  В **общие свойства**выберите **запускаемым проектом**, а затем нажмите кнопку **один запускаемый проект**.  
  
    3.  Из **один запускаемый проект** раскрывающегося списка, выберите **клиента**.  
  
    4.  Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.  
  
3.  Для построения образца нажмите CTRL+SHIFT+B.  
  
4.  Нажмите клавиши Ctrl + F5, чтобы запустить клиент.  
  
> [!NOTE]
>  Если эти шаги не работают, убедитесь, что вашей среде должным образом настроен, выполнив следующие действия:  
>   
> 1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
> 2.  Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](building-the-samples.md).  
> 3.  Чтобы запустить пример одного или нескольких конфигураций компьютеров, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a>См. также  
 [Образцы управления AppFabric](https://go.microsoft.com/fwlink/?LinkId=193960)
