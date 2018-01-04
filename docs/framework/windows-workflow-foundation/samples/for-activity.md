---
title: "Для действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3305defd4f2819a3ebe9d3b7429ddac11ae6833
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="for-activity"></a><span data-ttu-id="1f207-102">Для действия</span><span class="sxs-lookup"><span data-stu-id="1f207-102">For Activity</span></span>
<span data-ttu-id="1f207-103">В образце For демонстрируется построение пользовательского действия, которое наследует от <xref:System.Activities.NativeActivity> и используется в рабочем процессе для выполнения реального примера.</span><span class="sxs-lookup"><span data-stu-id="1f207-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="1f207-104">Пользовательское действие в этом образце работает подобно инструкции `for` языка C#.</span><span class="sxs-lookup"><span data-stu-id="1f207-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="1f207-105">T</span><span class="sxs-lookup"><span data-stu-id="1f207-105">T</span></span>  
  
 <span data-ttu-id="1f207-106">Пользовательское действие `For` имеет свойства `InitAction`, `IterationAction`, `Condition` и `Body`, которые соответствуют оператору инициализации, оператору итерации, условию продолжения и оператору тела, обычно присутствующим в стандартной инструкции `For` языка C#.</span><span class="sxs-lookup"><span data-stu-id="1f207-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="1f207-107">В следующей таблице описаны файлы ключа в образце.</span><span class="sxs-lookup"><span data-stu-id="1f207-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="1f207-108">Файл</span><span class="sxs-lookup"><span data-stu-id="1f207-108">File</span></span>|<span data-ttu-id="1f207-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1f207-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1f207-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="1f207-110">For.cs</span></span>|<span data-ttu-id="1f207-111">Определение класса для пользовательского действия `For`, которое расширяет класс <xref:System.Activities.NativeActivity> и обеспечивает функциональность, аналогичную оператору `For` языка C#.</span><span class="sxs-lookup"><span data-stu-id="1f207-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="1f207-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="1f207-112">Program.cs</span></span>|<span data-ttu-id="1f207-113">Клиентское приложение, которое выполняет базовый перебор (итерацию по) коллекции с помощью пользовательского действия `For`.</span><span class="sxs-lookup"><span data-stu-id="1f207-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="1f207-114">При применении пользовательского действия `For` убедитесь, что задано свойство `Condition`. В противном случае может произойти зацикливание.</span><span class="sxs-lookup"><span data-stu-id="1f207-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="1f207-115">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="1f207-115">Demonstrates</span></span>  
 <span data-ttu-id="1f207-116">Создайте пользовательское действие, которое наследует от класса <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="1f207-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="1f207-117">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="1f207-117">Discussion</span></span>  
 <span data-ttu-id="1f207-118">В следующей таблице представлено описание свойств действия, используемого в этом образце.</span><span class="sxs-lookup"><span data-stu-id="1f207-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="1f207-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="1f207-119">InitAction</span></span>  
 <span data-ttu-id="1f207-120">Инструкция инициализации</span><span class="sxs-lookup"><span data-stu-id="1f207-120">Initialization statement</span></span>  
  
 <span data-ttu-id="1f207-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="1f207-121">IterationAction</span></span>  
 <span data-ttu-id="1f207-122">Инструкция итерации</span><span class="sxs-lookup"><span data-stu-id="1f207-122">Iterative statement</span></span>  
  
 <span data-ttu-id="1f207-123">Условие</span><span class="sxs-lookup"><span data-stu-id="1f207-123">Condition</span></span>  
 <span data-ttu-id="1f207-124">Инструкция продолжения</span><span class="sxs-lookup"><span data-stu-id="1f207-124">Continuation statement</span></span>  
  
 <span data-ttu-id="1f207-125">Body</span><span class="sxs-lookup"><span data-stu-id="1f207-125">Body</span></span>  
 <span data-ttu-id="1f207-126">Инструкция текста (цикла)</span><span class="sxs-lookup"><span data-stu-id="1f207-126">Body statement</span></span>  
  
 <span data-ttu-id="1f207-127">Действие наследует от действия <xref:System.Activities.NativeActivity> для получения доступа к функциям времени выполнения, таким как планирование выполнения дополнительных действий с помощью одного из методов `ScheduleActivity` из контекста <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="1f207-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1f207-128">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="1f207-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="1f207-129">Откройте в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения For.sln.</span><span class="sxs-lookup"><span data-stu-id="1f207-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1f207-130">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="1f207-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1f207-131">Запустите решение, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="1f207-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1f207-132">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1f207-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1f207-133">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1f207-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1f207-134">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f207-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1f207-135">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1f207-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`