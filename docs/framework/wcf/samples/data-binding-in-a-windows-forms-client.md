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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b78cfbd63687fc7288c945ebcbec790150efed61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a><span data-ttu-id="ed30b-102">Привязка данных в клиенте Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ed30b-102">Data Binding in a Windows Forms Client</span></span>
<span data-ttu-id="ed30b-103">В этом примере показано, как выполнить привязку к данным, возвращаемым службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в приложении Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ed30b-103">This sample demonstrates how to bind to data returned by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Windows Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed30b-104">Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ed30b-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>  
  
 <span data-ttu-id="ed30b-105">В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="ed30b-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="ed30b-106">Этот образец состоит из приложения Windows Forms клиента (EXE) и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенной в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="ed30b-106">The sample consists of a client Windows Forms application (.exe) and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="ed30b-107">Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`.</span><span class="sxs-lookup"><span data-stu-id="ed30b-107">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="ed30b-108">Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.</span><span class="sxs-lookup"><span data-stu-id="ed30b-108">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="ed30b-109">Привязка данных выполняется на стороне клиента в приложении Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ed30b-109">The data binding occurs on the client in the Windows Forms application.</span></span> <span data-ttu-id="ed30b-110">`DataGridView` определяется в конструкторе Windows Forms, который является графическим представлением данных.</span><span class="sxs-lookup"><span data-stu-id="ed30b-110">A `DataGridView` is defined in the Windows Forms designer, which is a graphical representation of the data.</span></span> <span data-ttu-id="ed30b-111">Кроме того, создается посредник с именем `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="ed30b-111">An intermediary named `BindingSource` is also created.</span></span> <span data-ttu-id="ed30b-112">Источник данных `BindingSource` имеет значение массива данных, возвращаемых службой.</span><span class="sxs-lookup"><span data-stu-id="ed30b-112">The data source of `BindingSource` is set to the data array returned by the service.</span></span> <span data-ttu-id="ed30b-113">Предназначение источника данных `BindingSource` заключается в предоставлении уровня косвенного обращения между данными и представлением данных.</span><span class="sxs-lookup"><span data-stu-id="ed30b-113">The purpose of the `BindingSource` is to provide a layer of indirection between the data and the data view.</span></span> <span data-ttu-id="ed30b-114">Все взаимодействие с данными, такое как перемещение, сортировка, фильтрация и обновление, осуществляется посредством вызовов компонента `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="ed30b-114">All interaction with the data, such as navigating, sorting, filtering, and updating, is accomplished with calls to the `BindingSource` component.</span></span> <span data-ttu-id="ed30b-115">Чтобы выполнить привязку данных к `DataGridView`, источнику данных `datasource` объекта `DataGridView` присваивается значение объекта `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="ed30b-115">To accomplish data binding to the `DataGridView`, the `datasource` of the `DataGridView` is then set to the `BindingSource` object.</span></span> <span data-ttu-id="ed30b-116">Все данные, возвращаемые службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], представляются пользователю в графическом виде.</span><span class="sxs-lookup"><span data-stu-id="ed30b-116">All of the data returned from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is then displayed graphically to the user.</span></span>  <span data-ttu-id="ed30b-117">Каждый раз, когда пользователь нажимает кнопку, возвращаемые данные автоматически обновляются в объекте `DataGridView`, который использует привязку данных.</span><span class="sxs-lookup"><span data-stu-id="ed30b-117">Every time the user clicks the button, the returned data is automatically updated in the data-bound `DataGridView`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ed30b-118">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ed30b-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ed30b-119">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ed30b-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ed30b-120">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ed30b-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ed30b-121">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ed30b-121">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed30b-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed30b-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ed30b-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ed30b-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ed30b-124">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed30b-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ed30b-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ed30b-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a><span data-ttu-id="ed30b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ed30b-126">See Also</span></span>
