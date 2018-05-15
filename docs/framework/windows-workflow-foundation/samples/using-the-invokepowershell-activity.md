---
title: Использование действия InvokePowerShell
ms.date: 03/30/2017
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
ms.openlocfilehash: c5609556af94ed3e372538047ff6309a105975ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-invokepowershell-activity"></a><span data-ttu-id="6cad2-102">Использование действия InvokePowerShell</span><span class="sxs-lookup"><span data-stu-id="6cad2-102">Using the InvokePowerShell Activity</span></span>
<span data-ttu-id="6cad2-103">Образец InvokePowerShell демонстрирует, как вызывать команды Windows PowerShell с помощью действия `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-103">The InvokePowerShell sample demonstrates how to invoke Windows PowerShell commands using the `InvokePowerShell` activity.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6cad2-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="6cad2-104">Demonstrates</span></span>  
  
-   <span data-ttu-id="6cad2-105">Простой новый метод использования команд Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-105">Simple innovation of Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="6cad2-106">Получите значения из канала выходных данных Windows PowerShell и сохраните их в переменных рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6cad2-106">Retrieve values from the Windows PowerShell output pipeline and store them in workflow variables.</span></span>  
  
-   <span data-ttu-id="6cad2-107">Передайте данные в Windows PowerShell в виде канала входных данных для исполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="6cad2-107">Pass data into windows PowerShell as input pipeline for an executing command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6cad2-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6cad2-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6cad2-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6cad2-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6cad2-110">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="6cad2-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6cad2-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6cad2-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a><span data-ttu-id="6cad2-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="6cad2-112">Discussion</span></span>  
 <span data-ttu-id="6cad2-113">Этот образец содержит следующие три проекта.</span><span class="sxs-lookup"><span data-stu-id="6cad2-113">This sample contains the following three projects.</span></span>  
  
|<span data-ttu-id="6cad2-114">Имя проекта</span><span class="sxs-lookup"><span data-stu-id="6cad2-114">Project Name</span></span>|<span data-ttu-id="6cad2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6cad2-115">Description</span></span>|<span data-ttu-id="6cad2-116">Основные файлы</span><span class="sxs-lookup"><span data-stu-id="6cad2-116">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="6cad2-117">CodedClient</span><span class="sxs-lookup"><span data-stu-id="6cad2-117">CodedClient</span></span>|<span data-ttu-id="6cad2-118">Образец клиентского приложения, использующий действие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-118">A sample client application that uses the PowerShell activity.</span></span>|<span data-ttu-id="6cad2-119">-   **Program.cs**: программным образом создает рабочий процесс на основе последовательности, вызывающей действие InvokePowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-119">-   **Program.cs**: Programmatically creates a sequence-based workflow that calls the InvokePowerShell activity.</span></span>|  
|<span data-ttu-id="6cad2-120">DesignerClient</span><span class="sxs-lookup"><span data-stu-id="6cad2-120">DesignerClient</span></span>|<span data-ttu-id="6cad2-121">Набор пользовательских действий, содержащих пользовательское действие `InvokePowerShell`, прочие пользовательские действия и рабочий процесс, использующий их.</span><span class="sxs-lookup"><span data-stu-id="6cad2-121">A set of custom activities that contain the `InvokePowerShell` custom activity and other miscellaneous custom activities, and a workflow that uses them.</span></span>|<ul><li><span data-ttu-id="6cad2-122">Действия:</span><span class="sxs-lookup"><span data-stu-id="6cad2-122">Activities:</span></span><br /><br /> <ul><li><span data-ttu-id="6cad2-123">**PrintCollection.cs**: вспомогательное действие, выводящее все элементы в коллекции на консоль.</span><span class="sxs-lookup"><span data-stu-id="6cad2-123">**PrintCollection.cs**: A helper activity that prints all the items in a collection to the console.</span></span></li><li><span data-ttu-id="6cad2-124">**ReadLine.cs**: вспомогательное действие для чтения данные с консоли.</span><span class="sxs-lookup"><span data-stu-id="6cad2-124">**ReadLine.cs**: A helper activity for reading input from the console.</span></span></li></ul></li><li><span data-ttu-id="6cad2-125">Файловая система:</span><span class="sxs-lookup"><span data-stu-id="6cad2-125">File System:</span></span><br /><br /> <ul><li><span data-ttu-id="6cad2-126">**Copy.XAML**: действие, копирующее файл.</span><span class="sxs-lookup"><span data-stu-id="6cad2-126">**Copy.xaml**: An activity that copies a file.</span></span></li><li><span data-ttu-id="6cad2-127">**CreateFile.xaml**: действие, создающее файл.</span><span class="sxs-lookup"><span data-stu-id="6cad2-127">**CreateFile.xaml**: An activity that creates a file.</span></span></li><li><span data-ttu-id="6cad2-128">**DeleteFile.xaml**: действие, которое удаляет файл.</span><span class="sxs-lookup"><span data-stu-id="6cad2-128">**DeleteFile.xaml**: An activity that deletes a file.</span></span></li><li><span data-ttu-id="6cad2-129">**MakeDir.xaml**: действие, которое создает каталог.</span><span class="sxs-lookup"><span data-stu-id="6cad2-129">**MakeDir.xaml**: An activity that creates a directory.</span></span></li><li><span data-ttu-id="6cad2-130">**MOVE.XAML**: действие, перемещающее файл.</span><span class="sxs-lookup"><span data-stu-id="6cad2-130">**Move.xaml**: An activity that moves a file.</span></span></li><li><span data-ttu-id="6cad2-131">**ReadFile.xaml**: действие, которое считывает файл и возвращает его содержимое.</span><span class="sxs-lookup"><span data-stu-id="6cad2-131">**ReadFile.xaml**: An activity that reads a file and returns its contents.</span></span></li><li><span data-ttu-id="6cad2-132">**TestPath.xaml**: действие, проверяющее наличие пути.</span><span class="sxs-lookup"><span data-stu-id="6cad2-132">**TestPath.xaml**: An activity that tests for the existence of a path.</span></span></li></ul></li><li><span data-ttu-id="6cad2-133">Процесс:</span><span class="sxs-lookup"><span data-stu-id="6cad2-133">Process:</span></span><br /><br /> <ul><li><span data-ttu-id="6cad2-134">**GetProcess.xaml**: действие, возвращающее перечень запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="6cad2-134">**GetProcess.xaml**: An activity that gets a list of running processes.</span></span></li><li><span data-ttu-id="6cad2-135">**StopProcess.xaml**: действие, останавливающее конкретный процесс.</span><span class="sxs-lookup"><span data-stu-id="6cad2-135">**StopProcess.xaml**: An activity that stops a specific process.</span></span></li></ul></li><li><span data-ttu-id="6cad2-136">**Program.cs**: вызывает рабочий процесс Sequence1.</span><span class="sxs-lookup"><span data-stu-id="6cad2-136">**Program.cs**: Calls the Sequence1 workflow.</span></span></li><li><span data-ttu-id="6cad2-137">**Sequence1.XAML**: рабочий процесс на основе последовательности.</span><span class="sxs-lookup"><span data-stu-id="6cad2-137">**Sequence1.xaml**: A sequence-based workflow.</span></span></li></ul>|  
|<span data-ttu-id="6cad2-138">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cad2-138">PowerShell</span></span>|<span data-ttu-id="6cad2-139">Действие `InvokePowerShell` и связанные с ним конструкторы.</span><span class="sxs-lookup"><span data-stu-id="6cad2-139">The `InvokePowerShell` activity and its associated designers.</span></span>|<span data-ttu-id="6cad2-140">Файлы действия</span><span class="sxs-lookup"><span data-stu-id="6cad2-140">Activity Files</span></span><br /><br /> <span data-ttu-id="6cad2-141">-   **ExecutePowerShell.cs**: основной логики выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="6cad2-141">-   **ExecutePowerShell.cs**: The main execution logic of the activity.</span></span><br /><span data-ttu-id="6cad2-142">-   **InvokePowerShell.cs**: оболочка главной логики исполнения, который содержит стандартную (возвращающую значение) версию и нестандартную (не возвращающую значение) версию.</span><span class="sxs-lookup"><span data-stu-id="6cad2-142">-   **InvokePowerShell.cs**: The wrapper around the main execution logic, which contains a generic (return value) version and a non-generic (non-return value) version.</span></span> <span data-ttu-id="6cad2-143">Это открытый интерфейс действия.</span><span class="sxs-lookup"><span data-stu-id="6cad2-143">This is the public interface for the activity.</span></span><br /><span data-ttu-id="6cad2-144">-   **NoPersistZone.cs**: это действие препятствующее сохранению дочерних действий.</span><span class="sxs-lookup"><span data-stu-id="6cad2-144">-   **NoPersistZone.cs**: This activity prevents any child activities from persisting.</span></span> <span data-ttu-id="6cad2-145">Данный класс используется в реализации действия `InvokePowerShell` для предотвращения сохранения действия в ходе исполнения.</span><span class="sxs-lookup"><span data-stu-id="6cad2-145">This class is used within the `InvokePowerShell` activity implementation to prevent the activity from being persisted mid-execution.</span></span><br /><br /> <span data-ttu-id="6cad2-146">Файлы конструктора:</span><span class="sxs-lookup"><span data-stu-id="6cad2-146">Designer files:</span></span><br /><br /> <span data-ttu-id="6cad2-147">1.  **ArgumentDictionaryEditor.cs**: диалог Windows, который позволяет пользователю изменять аргументы `InvokePowerShell` действия.</span><span class="sxs-lookup"><span data-stu-id="6cad2-147">1.  **ArgumentDictionaryEditor.cs**: A Windows dialog that allows the user to edit the arguments of the `InvokePowerShell` activity.</span></span><br /><span data-ttu-id="6cad2-148">2.  **GenericInvokePowerShellDesigner.xaml** и **GenericInvokePowerShellDesigner.xaml.cs**: Определяет внешний вид универсального `InvokePowerShell` действия в [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cad2-148">2.  **GenericInvokePowerShellDesigner.xaml** and **GenericInvokePowerShellDesigner.xaml.cs**: Defines the appearance of the generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span><br /><span data-ttu-id="6cad2-149">3.  **InvokePowerShellDesigner.xaml** и **InvokePowerShellDesigner.cs**: Определяет внешний вид неуниверсальные `InvokePowerShell` действия в [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cad2-149">3.  **InvokePowerShellDesigner.xaml** and **InvokePowerShellDesigner.cs**: Defines the appearance of the non-generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>|  
  
 <span data-ttu-id="6cad2-150">Клиентские проекты обсуждаются в первую очередь, поскольку проще понять внутреннее функционирование действия PowerShell, изучив его практическое применение.</span><span class="sxs-lookup"><span data-stu-id="6cad2-150">The client projects are discussed first, as it is easier to understand the internal functionality of the PowerShell activity once its use is understood.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="6cad2-151">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="6cad2-151">Using This Sample</span></span>  
 <span data-ttu-id="6cad2-152">В следующих разделах описано, как использовать три проекта в образце.</span><span class="sxs-lookup"><span data-stu-id="6cad2-152">The following sections describe how to use the three projects in the sample.</span></span>  
  
### <a name="using-the-coded-client-project"></a><span data-ttu-id="6cad2-153">Использование закодированного клиентского проекта.</span><span class="sxs-lookup"><span data-stu-id="6cad2-153">Using the Coded Client Project</span></span>  
 <span data-ttu-id="6cad2-154">Образец клиента программным образом создает действие `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-154">The sample client programmatically creates a sequence activity, which contains examples of several different methods of using the `InvokePowerShell` activity.</span></span> <span data-ttu-id="6cad2-155">При первом вызове запускается блокнот.</span><span class="sxs-lookup"><span data-stu-id="6cad2-155">The first invocation launches Notepad.</span></span>  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 <span data-ttu-id="6cad2-156">При втором вызове возвращается перечень процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6cad2-156">The second invocation gets a list of the processes running on the local machine.</span></span>  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 <span data-ttu-id="6cad2-157">`Output` - это переменная, используемая для хранения выходных данных команды.</span><span class="sxs-lookup"><span data-stu-id="6cad2-157">`Output` is the variable used to store the output of the command.</span></span>  
  
 <span data-ttu-id="6cad2-158">При следующем вызове показывается, как запускать стадию завершающей обработки для каждого отдельного выхода вызова PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-158">The next call demonstrates how to run a post-processing step on each individual output of the PowerShell invocation.</span></span> <span data-ttu-id="6cad2-159">`InitializationAction` задается как функция, выводящая строчное представление каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="6cad2-159">`InitializationAction` is set to the function that outputs a string representation for each process.</span></span> <span data-ttu-id="6cad2-160">Коллекция этих строк возвращается в переменную `Output` действием `InvokePowerShell<string>`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-160">The collection of these strings is returned in the `Output` variable by the `InvokePowerShell<string>` activity.</span></span>  
  
 <span data-ttu-id="6cad2-161">При последующем вызове `InvokePowerShell` демонстрируется передача данных действию и вывод конечных данных и ошибок.</span><span class="sxs-lookup"><span data-stu-id="6cad2-161">The succeeding `InvokePowerShell` calls demonstrate passing data into the activity and getting outputs and errors out.</span></span>  
  
### <a name="using-the-designer-client-project"></a><span data-ttu-id="6cad2-162">Использование конструкторского клиентского проекта.</span><span class="sxs-lookup"><span data-stu-id="6cad2-162">Using the Designer Client Project</span></span>  
 <span data-ttu-id="6cad2-163">Проект DesignerClient состоит из набора пользовательских действий, большинство из которых содержат действие `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-163">The DesignerClient project consists of a set of custom activities, almost all of which are built containing the `InvokePowerShell` activity.</span></span> <span data-ttu-id="6cad2-164">Большинство действий вызывают нестандартную версию действия `InvokePowerShell` и не ожидают возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="6cad2-164">Most of the activities call the non-generic version of the `InvokePowerShell` activity, and do not expect a return value.</span></span> <span data-ttu-id="6cad2-165">Прочие действия применяют стандартную версию действия `InvokePowerShell` и аргумент `InitializationAction` для последующей обработки результатов.</span><span class="sxs-lookup"><span data-stu-id="6cad2-165">Other activities use the generic version of the `InvokePowerShell` activity, and use the `InitializationAction` argument to post-process the results.</span></span>  
  
## <a name="using-the-powershell-project"></a><span data-ttu-id="6cad2-166">Использование проекта PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cad2-166">Using the PowerShell Project</span></span>  
 <span data-ttu-id="6cad2-167">Главное действие действия совершается в классе `ExecutePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-167">The main action of the activity takes place in the `ExecutePowerShell` class.</span></span> <span data-ttu-id="6cad2-168">Поскольку исполнение команд PowerShell не должно блокировать поток главного рабочего процесса, действие создается как асинхронное путем наследования от класса <xref:System.Activities.AsyncCodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="6cad2-168">Because the execution of PowerShell commands should not block the main workflow thread, the activity is created to be an asynchronous activity by inheriting from the <xref:System.Activities.AsyncCodeActivity> class.</span></span>  
  
 <span data-ttu-id="6cad2-169">Метод <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> вызывается средой выполнения рабочего процесса, чтобы начать исполнение действия.</span><span class="sxs-lookup"><span data-stu-id="6cad2-169">The <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> method is called by the workflow runtime to begin running the activity.</span></span> <span data-ttu-id="6cad2-170">Для начала вызываются методы API-интерфейса PowerShell, чтобы создать конвейер PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-170">It starts by calling PowerShell APIs to create a PowerShell pipeline.</span></span>  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 <span data-ttu-id="6cad2-171">Затем создается команда PowerShell, которая заполняется параметрами и переменными.</span><span class="sxs-lookup"><span data-stu-id="6cad2-171">It then creates a PowerShell command and populates it with parameters and variables.</span></span>  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 <span data-ttu-id="6cad2-172">Входящие исходные данные в этот момент также отправляются в конвейер.</span><span class="sxs-lookup"><span data-stu-id="6cad2-172">The inputs piped in are also sent to the pipeline at this point.</span></span> <span data-ttu-id="6cad2-173">Наконец, конвейер получает оболочку из объекта `PipelineInvokerAsyncResult` и возвращается.</span><span class="sxs-lookup"><span data-stu-id="6cad2-173">Finally, the pipeline is wrapped in a `PipelineInvokerAsyncResult` object and returned.</span></span> <span data-ttu-id="6cad2-174">Объект `PipelineInvokerAsyncResult` регистрирует прослушиватель и вызывает конвейер.</span><span class="sxs-lookup"><span data-stu-id="6cad2-174">The `PipelineInvokerAsyncResult` object registers a listener and invokes the pipeline.</span></span>  
  
```  
pipeline.InvokeAsync();  
```  
  
 <span data-ttu-id="6cad2-175">После успешного выполнения конечные данные и ошибки сохраняются в том же объекте `PipelineInvokerAsyncResult`, а контроль возвращается среде выполнения рабочего процесса путем вызова метода обратного вызова, изначально переданного через параметр <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="6cad2-175">When execution finishes, output and errors are stored within the same `PipelineInvokerAsyncResult` object, and control is handed back to the workflow runtime by calling the callback method originally passed to <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span>  
  
 <span data-ttu-id="6cad2-176">В конце исполнения метода среда выполнения рабочего процесса вызывает метод <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> действия.</span><span class="sxs-lookup"><span data-stu-id="6cad2-176">At the end of the method's execution, the workflow runtime calls the activity’s <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> method.</span></span>  
  
 <span data-ttu-id="6cad2-177">Класс `InvokePowerShell` создает оболочку для класса `ExecutePowerShellCommand` и две версии действия: стандартную и нестандартную.</span><span class="sxs-lookup"><span data-stu-id="6cad2-177">The `InvokePowerShell` class wraps the `ExecutePowerShellCommand` class and creates two versions of the activity; a generic version and a non-generic version.</span></span> <span data-ttu-id="6cad2-178">Нестандартная версия возвращает конечные данные работы PowerShell непосредственно, а стандартная преобразует индивидуальные результаты в стандартный тип.</span><span class="sxs-lookup"><span data-stu-id="6cad2-178">The non-generic version returns the output of the PowerShell execution directly, whereas the generic version transforms the individual results to the generic type.</span></span>  
  
 <span data-ttu-id="6cad2-179">Стандартная версия действия реализуется как последовательный рабочий процесс, вызывающий команду `ExecutePowerShellCommand` и проводящий конечную обработку ее результатов.</span><span class="sxs-lookup"><span data-stu-id="6cad2-179">The generic version of the activity is implemented as a sequential workflow that calls `ExecutePowerShellCommand` and post-processes its results.</span></span> <span data-ttu-id="6cad2-180">Для каждого элемента из коллекции результатов на стадии конечной обработки вызывается действие `InitializationAction`. если оно задано.</span><span class="sxs-lookup"><span data-stu-id="6cad2-180">For each element in the result collection, the post-processing step calls `InitializationAction` if it is set.</span></span> <span data-ttu-id="6cad2-181">В противном случае осуществляется простое приведение.</span><span class="sxs-lookup"><span data-stu-id="6cad2-181">Otherwise, it does a simple cast.</span></span>  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 <span data-ttu-id="6cad2-182">Для каждого из двух действий `InvokePowerShell` (стандартного и нестандартного) создается конструктор.</span><span class="sxs-lookup"><span data-stu-id="6cad2-182">For each of the two `InvokePowerShell` activities (generic, and non-generic), a designer was created.</span></span> <span data-ttu-id="6cad2-183">InvokePowerShellDesigner.xaml и связанный с ним CS-файл определяют внешний вид в средстве [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] нестандартного действия `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-183">InvokePowerShellDesigner.xaml and its associated .cs file define the appearance in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] for the non-generic version of the `InvokePowerShell` activity.</span></span> <span data-ttu-id="6cad2-184">Внутри InvokePowerShellDesigner.xaml <xref:System.Windows.Controls.DockPanel> представляет графический интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6cad2-184">Inside InvokePowerShellDesigner.xaml, a <xref:System.Windows.Controls.DockPanel> is used to represent the graphical interface.</span></span>  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 <span data-ttu-id="6cad2-185">Стоит заметить, что свойство `Text` текстового поля является двусторонней привязкой, гарантирующей, что значение свойства `CommandText` действия будет эквивалентно значению, вводимому в конструктор.</span><span class="sxs-lookup"><span data-stu-id="6cad2-185">Note that the `Text` property of the text box is a two-way binding that ensures that the value of the activity’s `CommandText` property is equivalent to the value input into the designer.</span></span>  
  
 <span data-ttu-id="6cad2-186">GenericInvokePowerShellDesigner.xaml и связанный с ним CS-файл определяют графический интерфейс `InvokePowerShell` нестандартного действия.</span><span class="sxs-lookup"><span data-stu-id="6cad2-186">GenericInvokePowerShellDesigner.xaml and its associated .cs file define the graphical interface for the generic `InvokePowerShell` activity.</span></span> <span data-ttu-id="6cad2-187">Конструктор немного сложнее, поскольку позволяет пользователям задавать `InitializationAction`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-187">The designer is slightly more complicated because it allows users to set an `InitializationAction`.</span></span> <span data-ttu-id="6cad2-188">Ключевой элемент применения <xref:System.Activities.Presentation.WorkflowItemPresenter> - это возможность перетаскивать дочерние действия в область конструктора `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-188">The key element is the usage of <xref:System.Activities.Presentation.WorkflowItemPresenter> to allow drag and drop of child activities onto the `InvokePowerShell` designer surface.</span></span>  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 <span data-ttu-id="6cad2-189">Настройка конструктора не завершается настройкой XAML-файлов, определяющих внешний вид действия на холсте конструктора.</span><span class="sxs-lookup"><span data-stu-id="6cad2-189">The designer customization does not stop with the .xaml files that define the appearance of the activity on the design canvas.</span></span> <span data-ttu-id="6cad2-190">Диалоговые окна, используемые для отображения параметров действия, тоже можно настроить.</span><span class="sxs-lookup"><span data-stu-id="6cad2-190">The dialog boxes used to display the parameters of the activity can also be customized.</span></span> <span data-ttu-id="6cad2-191">Эти параметры и переменные PowerShell влияют на поведение команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-191">These parameters and PowerShell variables affect the behavior of PowerShell commands.</span></span> <span data-ttu-id="6cad2-192">Это действие предоставляет их в виде <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` типов.</span><span class="sxs-lookup"><span data-stu-id="6cad2-192">The activity exposes them as <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` types.</span></span> <span data-ttu-id="6cad2-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml и PropertyEditorResources.cs определяют диалоговое окно, позволяющее изменять эти типы.</span><span class="sxs-lookup"><span data-stu-id="6cad2-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml and PropertyEditorResources.cs define the dialog box that allows you to edit these types.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6cad2-194">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="6cad2-194">To set up, build, and run the sample</span></span>  
 <span data-ttu-id="6cad2-195">Чтобы запустить этот образец, нужно установить Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cad2-195">You must install Windows PowerShell to run this sample.</span></span> <span data-ttu-id="6cad2-196">Windows PowerShell можно установить из этого расположения: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span><span class="sxs-lookup"><span data-stu-id="6cad2-196">Windows PowerShell can be installed from this location: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span></span>  
  
#### <a name="to-run-the-coded-client"></a><span data-ttu-id="6cad2-197">Запуск закодированного клиента</span><span class="sxs-lookup"><span data-stu-id="6cad2-197">To run the coded client</span></span>  
  
1.  <span data-ttu-id="6cad2-198">Откройте файл PowerShell.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cad2-198">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="6cad2-199">Щелкните решение правой кнопкой мыши и постройте его.</span><span class="sxs-lookup"><span data-stu-id="6cad2-199">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="6cad2-200">Щелкните правой кнопкой мыши **CodedClient** проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="6cad2-200">Right-click the **CodedClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="6cad2-201">Нажмите CTRL+F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="6cad2-201">Press CTRL+F5 to run the application.</span></span>  
  
#### <a name="to-run-the-designer-client"></a><span data-ttu-id="6cad2-202">Запуск конструкторского клиента</span><span class="sxs-lookup"><span data-stu-id="6cad2-202">To run the designer client</span></span>  
  
1.  <span data-ttu-id="6cad2-203">Откройте файл PowerShell.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cad2-203">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="6cad2-204">Щелкните решение правой кнопкой мыши и постройте его.</span><span class="sxs-lookup"><span data-stu-id="6cad2-204">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="6cad2-205">Щелкните правой кнопкой мыши **DesignerClient** проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="6cad2-205">Right-click the **DesignerClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="6cad2-206">Нажмите CTRL+F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="6cad2-206">Press CTRL+F5 to run the application.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="6cad2-207">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="6cad2-207">Known Issues</span></span>  
  
1.  <span data-ttu-id="6cad2-208">Если при обращении к сборке с действиями `InvokePowerShell` или проекту от другого проекта возникает ошибка, возможно, нужно вручную добавить элемент `<SpecificVersion>True</SpecificVersion>` к CSPROJ-файлу нового проекта под строчкой, в которой происходит обращение к `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="6cad2-208">If referencing the `InvokePowerShell` activity assembly or project from another project results in a build error, you may need to manually add the `<SpecificVersion>True</SpecificVersion>` element to the .csproj file of the new project under the line that references `InvokePowerShell`.</span></span>  
  
2.  <span data-ttu-id="6cad2-209">Если не установлена оболочка Windows PowerShell, следующее сообщение об ошибке отображается в Visual Studio, сразу после добавления `InvokePowerShell` действия в рабочий процесс: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span><span class="sxs-lookup"><span data-stu-id="6cad2-209">If Windows PowerShell is not installed, the following error message is displayed in Visual Studio as soon as you add an `InvokePowerShell` activity onto a workflow: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span></span>  
  
3.  <span data-ttu-id="6cad2-210">В среде Windows PowerShell 2.0 не удался вызов `$input.MoveNext()` программным образом, а в скриптах, использующих `$input.MoveNext()`, формируются непреднамеренные ошибки и результаты.</span><span class="sxs-lookup"><span data-stu-id="6cad2-210">In Windows PowerShell 2.0, programmatically calling `$input.MoveNext()` fails and scripts using `$input.MoveNext()` produce unintended errors and results.</span></span> <span data-ttu-id="6cad2-211">Чтобы решить эту проблему, попробуйте использовать операцию PowerShell `foreach`, вместо того, чтобы вызывать `MoveNext()` при проходе по массиву.</span><span class="sxs-lookup"><span data-stu-id="6cad2-211">To work around this issue, consider using the PowerShell verb `foreach` instead of calling `MoveNext()` when iterating an array.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6cad2-212">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6cad2-212">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6cad2-213">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6cad2-213">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6cad2-214">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="6cad2-214">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6cad2-215">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6cad2-215">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`