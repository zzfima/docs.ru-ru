---
title: "Иерархическая модель конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbcef9ebe1b4876e429da97b3e217dd32286e4d6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="hierarchical-configuration-model"></a>Иерархическая модель конфигурации
Этот образец демонстрирует реализацию иерархии файлов конфигурации для служб. Он также показывает то, как привязки, поведения служб и конечных точек наследуются с более высоких уровней иерархии.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] разработано усовершенствование иерархической модели конфигурации. Примером модели иерархической конфигурации может служить модель, определенная файлом Machine.config -> Rootweb.config -> Web.config. В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] привязки и поведения, определенные на более высоких уровнях иерархии конфигурации, добавляются в службы без явной настройки. В этом образце показано, как можно упростить настройку служб с помощью элементов конфигурации, определенных на уровне компьютера или приложения.  
  
 В данном образце реализуется девять служб, которые распределяются по иерархии из трех уровней. В корне находится служба `Service1`. Службы `Service2` и `Service3` наследуют элементы по умолчанию от `Service1`. `Service4`, `Service5`, `Service6` и `Service7` определены на третьем уровне иерархии, наследуя элементы по умолчанию от `Service3`. Наконец, `Service10` и `Service11` находятся на четвертом уровне иерархии.  
  
 Все службы реализуют контракт `IDesc`. Далее приведено определение интерфейса `IDesc`, показывающее методы, доступ к которым имеется в этом интерфейсе. Интерфейс `IDesc` определен в файле Service1.cs.  
  
```  
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
  
    2.  В **общие свойства**выберите **запускаемый проект**, а затем нажмите кнопку **один запускаемый проект**.  
  
    3.  Из **один запускаемый проект** раскрывающийся список, выберите **клиента**.  
  
    4.  Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.  
  
3.  Для построения образца нажмите CTRL+SHIFT+B.  
  
4.  Нажмите клавиши Ctrl + F5, чтобы запустить клиент.  
  
> [!NOTE]
>  Если эти действия не дают результата, то проверьте правильность настройки среды, выполнив следующие действия.  
>   
>  1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
> 2.  Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
> 3.  Запуск образца одного или нескольких конфигураций на компьютере, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a>См. также  
 [Примеры управления AppFabric](http://go.microsoft.com/fwlink/?LinkId=193960)
