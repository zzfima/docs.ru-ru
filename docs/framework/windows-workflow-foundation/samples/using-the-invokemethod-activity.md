---
title: "Использование действия InvokeMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aacc20bf483877ac501fd8b35c04f6e3f9311afb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="b8469-102">Использование действия InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b8469-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="b8469-103">В этом примере демонстрируется использование <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) действию для вызова открытых методов открытых классов.</span><span class="sxs-lookup"><span data-stu-id="b8469-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="b8469-104"><!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Действия позволяет рабочему процессу вызывать методы для объектов, передавать параметры, получения возвращаемого значения, задавать типы универсальных методов и указать, является ли метод синхронным или асинхронные.</span><span class="sxs-lookup"><span data-stu-id="b8469-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="b8469-105">Неуниверсальном версии <xref:System.Activities.Statements.InvokeMethod> действия, в которых возвращаемое значение равно <xref:System.Activities.Statements.InvokeMethod.Result%2A> свойство и универсальная версия <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) действия которых возвращает возвращаемое значение через <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) свойство типа `TResult`.</span><span class="sxs-lookup"><span data-stu-id="b8469-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="b8469-106">В этом образце показано, как вызывать различные типы методов.</span><span class="sxs-lookup"><span data-stu-id="b8469-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="b8469-107">В следующем списке указаны типы методов, которые демонстрируются в этом образце:</span><span class="sxs-lookup"><span data-stu-id="b8469-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="b8469-108">Вызовите метод экземпляра без параметров.</span><span class="sxs-lookup"><span data-stu-id="b8469-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="b8469-109">Вызовите метод экземпляра с двумя параметрами (System.String и System.Int32).</span><span class="sxs-lookup"><span data-stu-id="b8469-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="b8469-110">Вызовите метод экземпляра с двумя параметрами (System.String и System.Int32) и массивом параметров типа System.String[].</span><span class="sxs-lookup"><span data-stu-id="b8469-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="b8469-111">Вызовите метод экземпляра с двумя параметрами (двумя числами System.Int32) и результатом типа System.Int32.</span><span class="sxs-lookup"><span data-stu-id="b8469-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="b8469-112">Возвращаемое значение привязано к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="b8469-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="b8469-113">Вызовите статический метод с двумя параметрами (System.String и System.Int32).</span><span class="sxs-lookup"><span data-stu-id="b8469-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="b8469-114">Вызовите метод экземпляра с одним универсальным параметром (System.String).</span><span class="sxs-lookup"><span data-stu-id="b8469-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="b8469-115">Вызовите статический метод с двумя универсальными параметрами (System.String и System.Int32).</span><span class="sxs-lookup"><span data-stu-id="b8469-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="b8469-116">Вызовите метод экземпляра, который имеет один параметр, передаваемый по ссылке (System.String).</span><span class="sxs-lookup"><span data-stu-id="b8469-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="b8469-117">Этот параметр, передаваемый по ссылке, привязан к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="b8469-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="b8469-118">Вызовите асинхронный метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b8469-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="b8469-119">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b8469-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="b8469-120">Откройте файл решения PInvokeMethodUsage.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8469-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b8469-121">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b8469-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b8469-122">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b8469-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8469-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8469-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b8469-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b8469-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b8469-125">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8469-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8469-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b8469-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`