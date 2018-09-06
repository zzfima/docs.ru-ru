---
title: Группа действий с условиями
ms.date: 03/30/2017
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
ms.openlocfilehash: 144a6c76ea6314c553e201fe4e2364890d869f34
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861209"
---
# <a name="conditioned-activity-group"></a><span data-ttu-id="d4d7d-102">Группа действий с условиями</span><span class="sxs-lookup"><span data-stu-id="d4d7d-102">Conditioned Activity Group</span></span>
<span data-ttu-id="d4d7d-103">В данном образце демонстрируется приложение бронирования путешествия.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-103">The sample demonstrates a travel booking application.</span></span> <span data-ttu-id="d4d7d-104">В объекте класса <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) содержатся два действия кода: действия "Car" и "Airline".</span><span class="sxs-lookup"><span data-stu-id="d4d7d-104">The <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) has two code activities: a Car activity and an Airline activity.</span></span> <span data-ttu-id="d4d7d-105">В конструкторе `SimpleCAGWorkflow` объект "ArrayList" с именем "travelNeedType" заполняется типами требуемых бронирования путешествия.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-105">In the `SimpleCAGWorkflow` constructor, a "travelNeedType" ArrayList object is populated with the types of travel bookings that are required.</span></span> <span data-ttu-id="d4d7d-106">При комментировании одной или обеих этих инструкций `travelNeeds.Add` поведение CAG соответствующим образом изменяется.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-106">By commenting out one or both of the `travelNeeds.Add` statements, you modify the CAG behavior accordingly.</span></span> <span data-ttu-id="d4d7d-107">В обоих действиях "Car" и "Airline" их условие <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>, заполнено объектом класса <xref:System.Workflow.Activities.CodeCondition>.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-107">Both the Car and Airline activities have their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> condition populated with a <xref:System.Workflow.Activities.CodeCondition>.</span></span> <span data-ttu-id="d4d7d-108">Действие Car выполняется, только если в коллекции `travelNeeds` есть запись `TravelNeeds.Car`; действие Airline выполняется только в том случае, если в коллекции `travelNeeds` содержится запись `TravelNeeds.Airline`.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-108">The Car activity executes only if the `travelNeeds` collection has a `TravelNeeds.Car` entry, and the Airline activity executes only if the `travelNeeds` collection has a `TravelNeeds.Airline` entry.</span></span>  
  
 <span data-ttu-id="d4d7d-109">При выполнении каждого из действий из коллекции удаляется соответствующая запись.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-109">The execution of each activity removes the corresponding entry from the collection.</span></span> <span data-ttu-id="d4d7d-110">Условие свойства <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> по умолчанию задает выход из CAG в том случае, если дочерние действия в настоящий момент не выполняются или готовы для выполнения (в зависимости от их условий <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>).</span><span class="sxs-lookup"><span data-stu-id="d4d7d-110">The default <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> condition specifies that the CAG should exit when no children are executing or are ready for execution (based on their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> conditions).</span></span> <span data-ttu-id="d4d7d-111">В данном образце это означает, что выход из CAG выполняется, если коллекция `travelNeeds` пуста.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-111">In this sample, this means that the CAG exits when the `travelNeeds` collection is empty.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="d4d7d-112">Сборка образца</span><span class="sxs-lookup"><span data-stu-id="d4d7d-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="d4d7d-113">Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4d7d-113">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d4d7d-114">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-114">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d4d7d-115">Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-115">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="d4d7d-116">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d4d7d-116">To run the sample</span></span>  
  
-   <span data-ttu-id="d4d7d-117">В окне командной строки пакета SDK запустите файл с расширением EXE в папке «SimpleCAG\bin\debug» (или в папке «SimpleCAG\bin» для образца в Visual Basic), вложенной в главную папку образца.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-117">In the SDK Command Prompt window, run the .exe file in the SimpleCAG\bin\debug folder (or the SimpleCAG\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d4d7d-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d4d7d-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d4d7d-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d4d7d-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d4d7d-121">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d4d7d-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a><span data-ttu-id="d4d7d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d4d7d-122">See Also</span></span>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
