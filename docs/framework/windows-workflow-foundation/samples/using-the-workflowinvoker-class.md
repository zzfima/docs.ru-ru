---
title: "Использование класса WorkflowInvoker"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 553367916ff249118a8fcdd8273382402b90cfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="17a7e-102">Использование класса WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="17a7e-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="17a7e-103">В этом образце показано, как использовать класс <xref:System.Activities.WorkflowInvoker> для вызова действия, как если бы это был метод.</span><span class="sxs-lookup"><span data-stu-id="17a7e-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="17a7e-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="17a7e-104">Sample Details</span></span>  
 <span data-ttu-id="17a7e-105">Использование класса <xref:System.Activities.WorkflowInvoker> - самый простой способ выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="17a7e-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="17a7e-106">Класс создан для запуска действия напрямую, как будто это вызов метода.</span><span class="sxs-lookup"><span data-stu-id="17a7e-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="17a7e-107">Это простой, быстродействующий и удобный API-интерфейс для использования в сценариях, в которых исполнение действия не требует инфраструктуры контроля, которую предоставляют другие варианты размещения.</span><span class="sxs-lookup"><span data-stu-id="17a7e-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="17a7e-108">В образце используется настраиваемое действие, которое является производным от <xref:System.Activities.CodeActivity%601>< Int32\> с именем `Add` , добавляющий два <xref:System.Activities.InArgument%601>, `X` и `Y`и возвращает `Result` <xref:System.Activities.OutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="17a7e-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="17a7e-109">(<xref:System.Activities.CodeActivity%601>\<T > является производным от <xref:System.Activities.Activity%601>< T\>, который имеет <xref:System.Activities.OutArgument%601> \<T > с именем `Result`.) Объект `Dictionary` \<строка, объект > используется для передачи аргументов действию, вызываемому посредством <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="17a7e-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="17a7e-110">Ключ словаря соответствует имени аргумента для вызываемого действия.</span><span class="sxs-lookup"><span data-stu-id="17a7e-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="17a7e-111">Значение, связанное с определенным ключом, привязано к аргументу, идентифицируемому ключом.</span><span class="sxs-lookup"><span data-stu-id="17a7e-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="17a7e-112">В образце выполняется вызов метода <xref:System.Activities.WorkflowInvoker.Invoke%2A> и передача словаря, который содержит значения для аргументов `X` и `Y`.</span><span class="sxs-lookup"><span data-stu-id="17a7e-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="17a7e-113">Класс <xref:System.Activities.WorkflowInvoker> привязывает эти значения к аргументам действия `Add`, выполняет действие и возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="17a7e-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="17a7e-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="17a7e-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="17a7e-115">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения Invoker.sln.</span><span class="sxs-lookup"><span data-stu-id="17a7e-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="17a7e-116">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="17a7e-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="17a7e-117">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="17a7e-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="17a7e-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17a7e-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="17a7e-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="17a7e-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="17a7e-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17a7e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="17a7e-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="17a7e-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`