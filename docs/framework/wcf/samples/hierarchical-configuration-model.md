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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b3b170e3e6453c14f557786572c54ac6f67c3db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hierarchical-configuration-model"></a><span data-ttu-id="e3972-102">Иерархическая модель конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3972-102">Hierarchical Configuration Model</span></span>
<span data-ttu-id="e3972-103">Этот образец демонстрирует реализацию иерархии файлов конфигурации для служб.</span><span class="sxs-lookup"><span data-stu-id="e3972-103">This sample demonstrates how to implement a hierarchy of configuration files for services.</span></span> <span data-ttu-id="e3972-104">Он также показывает то, как привязки, поведения служб и конечных точек наследуются с более высоких уровней иерархии.</span><span class="sxs-lookup"><span data-stu-id="e3972-104">It also shows how bindings, service behaviors, and endpoint behaviors are inherited from higher levels in the hierarchy.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="e3972-105">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="e3972-105">Sample details</span></span>  
 <span data-ttu-id="e3972-106">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] разработано усовершенствование иерархической модели конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e3972-106">One of the features developed for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] is the improvement in the hierarchical configuration model.</span></span> <span data-ttu-id="e3972-107">Примером модели иерархической конфигурации может служить модель, определенная файлом Machine.config -> Rootweb.config -> Web.config. В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] привязки и поведения, определенные на более высоких уровнях иерархии конфигурации, добавляются в службы без явной настройки.</span><span class="sxs-lookup"><span data-stu-id="e3972-107">An example of a hierarchical configuration model would be the one defined by Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], those bindings and behaviors that are defined in upper levels in the configuration hierarchy are added to your services with no explicit configuration.</span></span> <span data-ttu-id="e3972-108">В этом образце показано, как можно упростить настройку служб с помощью элементов конфигурации, определенных на уровне компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="e3972-108">This sample shows how it is possible to simplify your service configuration by relying on configuration elements defined at the computer or the application level.</span></span>  
  
 <span data-ttu-id="e3972-109">В данном образце реализуется девять служб, которые распределяются по иерархии из трех уровней.</span><span class="sxs-lookup"><span data-stu-id="e3972-109">This sample consists of nine services, defined in three levels of hierarchy.</span></span> <span data-ttu-id="e3972-110">В корне находится служба `Service1`.</span><span class="sxs-lookup"><span data-stu-id="e3972-110">`Service1` is at the root.</span></span> <span data-ttu-id="e3972-111">Службы `Service2` и `Service3` наследуют элементы по умолчанию от `Service1`.</span><span class="sxs-lookup"><span data-stu-id="e3972-111">`Service2` and `Service3` inherit the default elements from `Service1`.</span></span> <span data-ttu-id="e3972-112">`Service4`, `Service5`, `Service6` и `Service7` определены на третьем уровне иерархии, наследуя элементы по умолчанию от `Service3`.</span><span class="sxs-lookup"><span data-stu-id="e3972-112">`Service4`, `Service5`, `Service6` and `Service7` are defined at a third level of the hierarchy, inheriting the default elements from `Service3`.</span></span> <span data-ttu-id="e3972-113">Наконец, `Service10` и `Service11` находятся на четвертом уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="e3972-113">Finally `Service10` and `Service11` are at a fourth level of the hierarchy.</span></span>  
  
 <span data-ttu-id="e3972-114">Все службы реализуют контракт `IDesc`.</span><span class="sxs-lookup"><span data-stu-id="e3972-114">All the services implement the `IDesc` contract.</span></span> <span data-ttu-id="e3972-115">Далее приведено определение интерфейса `IDesc`, показывающее методы, доступ к которым имеется в этом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="e3972-115">The following is the definition of the `IDesc` interface that shows the methods exposed in this interface.</span></span> <span data-ttu-id="e3972-116">Интерфейс `IDesc` определен в файле Service1.cs.</span><span class="sxs-lookup"><span data-stu-id="e3972-116">The `IDesc` interface is defined in Service1.cs.</span></span>  
  
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
  
 <span data-ttu-id="e3972-117">Службы непосредственно реализуют эти методы.</span><span class="sxs-lookup"><span data-stu-id="e3972-117">The implementation of these methods by the services is straightforward.</span></span> <span data-ttu-id="e3972-118">`ListEndpoints` проходит по всем конечным точкам службы и возвращает список всех конечных точек, которые имеет служба.</span><span class="sxs-lookup"><span data-stu-id="e3972-118">`ListEndpoints` iterates through all the service endpoints and returns a list of all the endpoints that the service has.</span></span> <span data-ttu-id="e3972-119">`ListServiceBehaviors` проходит по всем поведениям, добавленным в службу, и возвращает список всех поведений службы, связанных с ней.</span><span class="sxs-lookup"><span data-stu-id="e3972-119">`ListServiceBehaviors` iterates through all the behaviors added to the service and returns the list of all the service behaviors associated with the service.</span></span> <span data-ttu-id="e3972-120">`ListEndpointBehaviors` действует так же, как `ListServiceBehaviors`, но возвращает список поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e3972-120">`ListEndpointBehaviors` behaves in a similar way to `ListServiceBehaviors`, but it returns the list of endpoint behaviors instead.</span></span>  
  
 <span data-ttu-id="e3972-121">Благодаря этой реализации клиент знает, сколько конечных точек имеет служба, а также какие поведения службы и конечной точки добавлены в службу.</span><span class="sxs-lookup"><span data-stu-id="e3972-121">This implementation allows the client to know how many endpoints the service is exposing and which service behaviors and endpoint behaviors have been added to the service.</span></span> <span data-ttu-id="e3972-122">Клиент, реализованный как часть образца, добавляет ссылку на службу во все службы решения и показывает эти элементы для всех служб.</span><span class="sxs-lookup"><span data-stu-id="e3972-122">The client that has been implemented as part of the sample adds a service reference to all the services in the solution and shows these elements for each one of the services.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="e3972-123">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="e3972-123">To use this sample</span></span>  
  
#### <a name="to-run-the-client"></a><span data-ttu-id="e3972-124">Запуск клиента</span><span class="sxs-lookup"><span data-stu-id="e3972-124">To run the client</span></span>  
  
1.  <span data-ttu-id="e3972-125">Откройте файл ConfigHierarchicalModel.sln с помощью [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3972-125">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ConfigHierarchicalModel.sln file.</span></span>  
  
2.  <span data-ttu-id="e3972-126">Проект клиента еще не установлен в качестве запускаемого проекта; выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e3972-126">The client project is not already set up as the start-up project, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="e3972-127">В **обозревателе решений**, щелкните правой кнопкой мыши решение и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e3972-127">In **Solution Explorer**, right-click the solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="e3972-128">В **общие свойства**выберите **запускаемый проект**, а затем нажмите кнопку **один запускаемый проект**.</span><span class="sxs-lookup"><span data-stu-id="e3972-128">In **Common Properties**, select **Startup Project**, and then click **Single startup project**.</span></span>  
  
    3.  <span data-ttu-id="e3972-129">Из **один запускаемый проект** раскрывающийся список, выберите **клиента**.</span><span class="sxs-lookup"><span data-stu-id="e3972-129">From the **Single startup project** drop-down, select **Client**.</span></span>  
  
    4.  <span data-ttu-id="e3972-130">Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e3972-130">Click **OK** to close the dialog.</span></span>  
  
3.  <span data-ttu-id="e3972-131">Для построения образца нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="e3972-131">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="e3972-132">Нажмите клавиши Ctrl + F5, чтобы запустить клиент.</span><span class="sxs-lookup"><span data-stu-id="e3972-132">To run the client, press Ctrl+F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3972-133">Если эти действия не дают результата, то проверьте правильность настройки среды, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e3972-133">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="e3972-134">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3972-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="e3972-135">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3972-135">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="e3972-136">Запуск образца одного или нескольких конфигураций на компьютере, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3972-136">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3972-137">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3972-137">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e3972-138">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e3972-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e3972-139">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3972-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e3972-140">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e3972-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a><span data-ttu-id="e3972-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e3972-141">See Also</span></span>  
 [<span data-ttu-id="e3972-142">Примеры управления AppFabric</span><span class="sxs-lookup"><span data-stu-id="e3972-142">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)
