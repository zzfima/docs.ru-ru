---
title: InvokeMethod
ms.date: 03/30/2017
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
ms.openlocfilehash: 12d028515c34c0e3593c90b81a5589fb05f36b82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="invokemethod"></a><span data-ttu-id="98f2e-102">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="98f2e-102">InvokeMethod</span></span>
<span data-ttu-id="98f2e-103">В этом образце демонстрируются разные способы использования действия <xref:System.Activities.Statements.InvokeMethod> для вызова методов класса.</span><span class="sxs-lookup"><span data-stu-id="98f2e-103">This sample shows the different ways of using the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 <span data-ttu-id="98f2e-104">Метод относится к классу и представляет содержащийся набор операций.</span><span class="sxs-lookup"><span data-stu-id="98f2e-104">A method belongs to a class and represents a contained set of operations.</span></span> <span data-ttu-id="98f2e-105">Действие <xref:System.Activities.Statements.InvokeMethod> предоставляет возможность вызова методов относительно объектов или типов, передачи параметров и получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="98f2e-105">The <xref:System.Activities.Statements.InvokeMethod> activity gives you the ability to call methods against objects or types, pass in parameters, and get the return value.</span></span> <span data-ttu-id="98f2e-106">Методы могут быть вызваны синхронно и асинхронно.</span><span class="sxs-lookup"><span data-stu-id="98f2e-106">Methods can be invoked synchronously or asynchronously.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="98f2e-107">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="98f2e-107">Sample Details</span></span>  
 <span data-ttu-id="98f2e-108">В этом образце используется действие <xref:System.Activities.Statements.InvokeMethod> для выполнения следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="98f2e-108">This sample uses the <xref:System.Activities.Statements.InvokeMethod> activity to perform the following scenarios:</span></span>  
  
1.  <span data-ttu-id="98f2e-109">Вызовите метод экземпляра без параметров.</span><span class="sxs-lookup"><span data-stu-id="98f2e-109">Invoke an instance method without parameters.</span></span>  
  
2.  <span data-ttu-id="98f2e-110">Вызовите метод экземпляра с двумя параметрами (<xref:System.String> и <xref:System.Int32>).</span><span class="sxs-lookup"><span data-stu-id="98f2e-110">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>).</span></span>  
  
3.  <span data-ttu-id="98f2e-111">Вызовите метод экземпляр с двумя параметрами (<xref:System.String> и <xref:System.Int32>) и массивом параметров типа <xref:System.String>[].</span><span class="sxs-lookup"><span data-stu-id="98f2e-111">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>) and a parameter array of type <xref:System.String>[].</span></span>  
  
4.  <span data-ttu-id="98f2e-112">Вызовите метод экземпляра с двумя параметрами типа <xref:System.Int32> и результатом типа <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-112">Invoke an instance method with two parameters of type <xref:System.Int32> and a result of type <xref:System.Int32>.</span></span> <span data-ttu-id="98f2e-113">В этом сценарии значение результата привязано к переменной и используется в другом действии.</span><span class="sxs-lookup"><span data-stu-id="98f2e-113">In this scenario, the result value is bound to a variable and used in another activity.</span></span> <span data-ttu-id="98f2e-114">Значение отображается в консоли при помощи действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-114">It is displayed in the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
5.  <span data-ttu-id="98f2e-115">Вызовите статический метод экземпляра с двумя параметрами типа <xref:System.String> и <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-115">Invoke a static method with two parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
6.  <span data-ttu-id="98f2e-116">Вызовите метод экземпляра с одним общим параметром типа <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-116">Invoke an instance method with one generic parameter of type <xref:System.String>.</span></span>  
  
7.  <span data-ttu-id="98f2e-117">Вызовите статический метод с двумя общими параметрами типа <xref:System.String> и <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-117">Invoke a static method with two generic parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
8.  <span data-ttu-id="98f2e-118">Вызовите метод экземпляра, который имеет один параметр типа <xref:System.String>, переданный по ссылке.</span><span class="sxs-lookup"><span data-stu-id="98f2e-118">Invoke an instance method that has one parameter passed by reference of type <xref:System.String>.</span></span> <span data-ttu-id="98f2e-119">В этом сценарии параметр ссылки привязан к переменной (`outParam`) и используется в другом действии.</span><span class="sxs-lookup"><span data-stu-id="98f2e-119">In this scenario, the reference parameter is bound to a variable (`outParam`) and used in another activity.</span></span> <span data-ttu-id="98f2e-120">Параметр отображается в консоли при помощи действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-120">It is displayed on the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
9. <span data-ttu-id="98f2e-121">Вызовите асинхронный метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="98f2e-121">Invoke an asynchronous instance method.</span></span>  
  
10. <span data-ttu-id="98f2e-122">Вызовите два других действия относительно одного и того же объекта при помощи двух действий <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="98f2e-122">Invoke two different methods on the same instance of an object using two <xref:System.Activities.Statements.InvokeMethod> activities.</span></span>  
  
11. <span data-ttu-id="98f2e-123">Сохраните значение в экземпляре объекта.</span><span class="sxs-lookup"><span data-stu-id="98f2e-123">Store a value in an instance of an object.</span></span>  
  
12. <span data-ttu-id="98f2e-124">Извлеките значение из экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="98f2e-124">Retrieve a value from an instance of an object.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="98f2e-125">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="98f2e-125">To use this sample</span></span>  
 <span data-ttu-id="98f2e-126">Данный образец предоставляется в двух версиях.</span><span class="sxs-lookup"><span data-stu-id="98f2e-126">This sample is provided in two versions.</span></span> <span data-ttu-id="98f2e-127">В первой версии образца показано использование <xref:System.Activities.Statements.InvokeMethod> посредством кода C# с помощью модели программирования Windows Workflow Foundation (WF), которые находятся в папке CodedWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="98f2e-127">The first version of this sample demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> through C# code using the Windows Workflow Foundation (WF) programming model and can be found under the CodedWorkflow\CS folder.</span></span> <span data-ttu-id="98f2e-128">Во второй версии показано использование метода <xref:System.Activities.Statements.InvokeMethod> при помощи XAML; версия находится под папкой DesignerWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="98f2e-128">The second version demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> using XAML and can be found under the DesignerWorkflow\CS folder.</span></span>  
  
#### <a name="to-run-the-coded-workflow-sample"></a><span data-ttu-id="98f2e-129">Выполнение образца кода рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="98f2e-129">To run the coded workflow sample</span></span>  
  
1.  <span data-ttu-id="98f2e-130">Откройте файл решения InvokeMethodUsage.sln из папки CodedWorkflow\CS в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98f2e-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the CodedWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="98f2e-131">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="98f2e-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="98f2e-132">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="98f2e-132">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-designer-workflow-sample"></a><span data-ttu-id="98f2e-133">Выполнение образца рабочего процесса конструктора</span><span class="sxs-lookup"><span data-stu-id="98f2e-133">To run the designer workflow sample</span></span>  
  
1.  <span data-ttu-id="98f2e-134">Откройте файл решения InvokeMethodUsage.sln из папки DesignerWorkflow\CS в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98f2e-134">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the DesignerWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="98f2e-135">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="98f2e-135">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="98f2e-136">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="98f2e-136">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="98f2e-137">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="98f2e-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="98f2e-138">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="98f2e-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="98f2e-139">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="98f2e-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="98f2e-140">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="98f2e-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`