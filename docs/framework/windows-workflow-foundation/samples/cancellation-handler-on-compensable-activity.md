---
title: "Обработчик отмены действия, подлежащего компенсации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b39b5d9277767160225a34be9e0c71a36e7b6d78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="114c3-102">Обработчик отмены действия, подлежащего компенсации</span><span class="sxs-lookup"><span data-stu-id="114c3-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="114c3-103">В этом образце показано использование обработчика отмены в <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="114c3-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="114c3-104">Образец содержит два сценария, демонстрирующих использования отмены <xref:System.Activities.Statements.CompensableActivity>. Первый сценарий содержит корневое действие, подлежащее компенсации, включающее в себя три дочерних действия, подлежащих компенсации.</span><span class="sxs-lookup"><span data-stu-id="114c3-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="114c3-105">Два дочерних действия успешно заканчивают выполнение своих действий.</span><span class="sxs-lookup"><span data-stu-id="114c3-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="114c3-106">Когда выполняется текст третьего дочернего действия, встречает исключение, осуществляющее отмену обработки третьего действия, что вызывает, в свою очередь, отмену корневого действия.</span><span class="sxs-lookup"><span data-stu-id="114c3-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="114c3-107">Логика корневого действия в данном примере состоит в компенсации двух других дочерних действий, завершившихся ранее.</span><span class="sxs-lookup"><span data-stu-id="114c3-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="114c3-108">Второй сценарий демонстрирует выполнение <xref:System.Activities.Statements.TryCatch> параллельно с <xref:System.Activities.Statements.Delay>, завершающееся до ветви <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="114c3-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="114c3-109">Для условия завершения устанавливается значение `true` после завершения выполнения первой ветви, в результате чего вторая ветвь отменяется.</span><span class="sxs-lookup"><span data-stu-id="114c3-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="114c3-110">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="114c3-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="114c3-111">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте CompensationCancellation.sln.</span><span class="sxs-lookup"><span data-stu-id="114c3-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="114c3-112">Выполните сборку образца, нажав сочетание клавиш CTRL+SHIFT+B, или выберите команду «Выполнить сборку решения» в меню «Сборка».</span><span class="sxs-lookup"><span data-stu-id="114c3-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="114c3-113">Запустите образец, нажав F5, или выберите команду Начать отладку в меню Отладка.</span><span class="sxs-lookup"><span data-stu-id="114c3-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="114c3-114">Другой способ - нажать Ctrl+F5 или выбрать команду Запуск без отладки в меню Отладка.</span><span class="sxs-lookup"><span data-stu-id="114c3-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="114c3-115">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="114c3-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="114c3-116">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="114c3-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="114c3-117">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="114c3-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="114c3-118">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="114c3-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`  
  
## <a name="see-also"></a><span data-ttu-id="114c3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="114c3-119">See Also</span></span>
