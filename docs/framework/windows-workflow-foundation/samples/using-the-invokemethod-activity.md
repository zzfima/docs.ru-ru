---
title: Использование действия InvokeMethod
ms.date: 03/30/2017
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
ms.openlocfilehash: f6e32d002a4a2002037a6d74c5a2c3e275568efb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="06f1e-102">Использование действия InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="06f1e-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="06f1e-103">В этом примере демонстрируется использование <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) действию для вызова открытых методов открытых классов.</span><span class="sxs-lookup"><span data-stu-id="06f1e-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="06f1e-104"><!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Действия позволяет рабочему процессу вызывать методы для объектов, передавать параметры, получения возвращаемого значения, задавать типы универсальных методов и указать, является ли метод синхронным или асинхронные.</span><span class="sxs-lookup"><span data-stu-id="06f1e-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="06f1e-105">Неуниверсальном версии <xref:System.Activities.Statements.InvokeMethod> действия, в которых возвращаемое значение равно <xref:System.Activities.Statements.InvokeMethod.Result%2A> свойство и универсальная версия <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) действия которых возвращает возвращаемое значение через <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) свойство типа `TResult`.</span><span class="sxs-lookup"><span data-stu-id="06f1e-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="06f1e-106">В этом образце показано, как вызывать различные типы методов.</span><span class="sxs-lookup"><span data-stu-id="06f1e-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="06f1e-107">В следующем списке указаны типы методов, которые демонстрируются в этом образце:</span><span class="sxs-lookup"><span data-stu-id="06f1e-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="06f1e-108">Вызовите метод экземпляра без параметров.</span><span class="sxs-lookup"><span data-stu-id="06f1e-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="06f1e-109">Вызовите метод экземпляра с двумя параметрами (System.String и System.Int32).</span><span class="sxs-lookup"><span data-stu-id="06f1e-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="06f1e-110">Вызовите метод экземпляра с двумя параметрами (System.String и System.Int32) и массивом параметров типа System.String[].</span><span class="sxs-lookup"><span data-stu-id="06f1e-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="06f1e-111">Вызовите метод экземпляра с двумя параметрами (двумя числами System.Int32) и результатом типа System.Int32.</span><span class="sxs-lookup"><span data-stu-id="06f1e-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="06f1e-112">Возвращаемое значение привязано к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="06f1e-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="06f1e-113">Вызовите статический метод с двумя параметрами (System.String и System.Int32).</span><span class="sxs-lookup"><span data-stu-id="06f1e-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="06f1e-114">Вызовите метод экземпляра с одним универсальным параметром (System.String).</span><span class="sxs-lookup"><span data-stu-id="06f1e-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="06f1e-115">Вызовите статический метод с двумя универсальными параметрами (System.String и System.Int32).</span><span class="sxs-lookup"><span data-stu-id="06f1e-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="06f1e-116">Вызовите метод экземпляра, который имеет один параметр, передаваемый по ссылке (System.String).</span><span class="sxs-lookup"><span data-stu-id="06f1e-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="06f1e-117">Этот параметр, передаваемый по ссылке, привязан к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="06f1e-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="06f1e-118">Вызовите асинхронный метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="06f1e-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="06f1e-119">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="06f1e-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="06f1e-120">Откройте файл решения PInvokeMethodUsage.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06f1e-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="06f1e-121">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="06f1e-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="06f1e-122">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="06f1e-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="06f1e-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="06f1e-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="06f1e-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="06f1e-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="06f1e-125">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="06f1e-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="06f1e-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="06f1e-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`