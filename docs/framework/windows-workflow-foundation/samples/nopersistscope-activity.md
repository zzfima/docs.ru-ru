---
title: "Действие NoPersistScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8813739f9e2f22cb94ed353f73a64562d3aeaa84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="nopersistscope-activity"></a><span data-ttu-id="e2b14-102">Действие NoPersistScope</span><span class="sxs-lookup"><span data-stu-id="e2b14-102">NoPersistScope Activity</span></span>
<span data-ttu-id="e2b14-103">В этом образце показано, как обрабатывать несериализуемое и высвобождаемое состояние в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="e2b14-103">This sample shows how to manipulate a non-serializable and disposable state within a workflow.</span></span> <span data-ttu-id="e2b14-104">Важно заметить, что попыток сохранения несериализуемого состояния в рабочих процессах не происходит. Кроме того, необходимо очищать высвобождаемые объекты после их использования в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="e2b14-104">It is important that workflows do not attempt to persist non-serializable state and it is also important for disposable objects to be cleaned up after they are used in workflow.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e2b14-105">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="e2b14-105">Demonstrates</span></span>  
 <span data-ttu-id="e2b14-106">Настраиваемое действие `NoPersistScope` и его конструктор.</span><span class="sxs-lookup"><span data-stu-id="e2b14-106">`NoPersistScope` custom activity and designer.</span></span>  
  
## <a name="using-the-nopersistzone-activity"></a><span data-ttu-id="e2b14-107">Использование действия NoPersistZone</span><span class="sxs-lookup"><span data-stu-id="e2b14-107">Using the NoPersistZone activity</span></span>  
 <span data-ttu-id="e2b14-108">При запуске данного образца рабочего процесса пользовательское действие `CreateTextWriter` создает объект типа <xref:System.IO.TextWriter> и сохраняет его в переменной рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e2b14-108">When the sample workflow runs, a custom activity called `CreateTextWriter` creates an object of type <xref:System.IO.TextWriter> and saves it into a workflow variable.</span></span> <span data-ttu-id="e2b14-109">Параметр <xref:System.IO.TextWriter> является объектом <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="e2b14-109"><xref:System.IO.TextWriter> is an <xref:System.IDisposable> object.</span></span> <span data-ttu-id="e2b14-110">Данный модуль записи <xref:System.IO.TextWriter>, настроенный на запись в файл "out.txt" в директории, из которой запущен образец, используется действием <xref:System.Activities.Statements.WriteLine>, когда оно копирует какой-либо текст, вводимый с консоли.</span><span class="sxs-lookup"><span data-stu-id="e2b14-110">This <xref:System.IO.TextWriter>, which is configured to write to a file named ‘out.txt’ in the directory in which the sample runs, is used by a <xref:System.Activities.Statements.WriteLine> activity as it echoes any text you type in at the console.</span></span>  
  
 <span data-ttu-id="e2b14-111">Логика копирования действует в рамках действия `NoPersistScope` (код для которого также является частью данного образца), что препятствует сохранению рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e2b14-111">The echo logic runs within a `NoPersistScope` activity (the code for which is also part of this sample), which prevents the workflow from being persisted.</span></span> <span data-ttu-id="e2b14-112">При вводе в `unload` на консоль, узел попытается сохранить экземпляр рабочего процесса, но время ожидания для этой операции, поскольку рабочий процесс остается в `NoPersistScope`.</span><span class="sxs-lookup"><span data-stu-id="e2b14-112">If you type in `unload` at the console, the host attempts to persist the workflow instance but this operation times out because the workflow remains within a `NoPersistScope`.</span></span> <span data-ttu-id="e2b14-113">Рабочий процесс также применяет настраиваемое действие под названием `Dispose`, чтобы удалить объект <xref:System.IO.TextWriter>, когда он больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="e2b14-113">The workflow also utilizes a custom activity called `Dispose` to dispose the <xref:System.IO.TextWriter> object when the workflow is finished using it.</span></span> <span data-ttu-id="e2b14-114">Действие `Dispose` помещается в блоке <xref:System.Activities.Statements.TryCatch.Finally%2A> действия <xref:System.Activities.Statements.TryCatch>, в котором объявляется переменная <xref:System.IO.TextWriter>, чтобы гарантировать ее запуск даже при формировании исключения в ходе работы блока Try.</span><span class="sxs-lookup"><span data-stu-id="e2b14-114">The `Dispose` activity is placed within the <xref:System.Activities.Statements.TryCatch.Finally%2A> block of the <xref:System.Activities.Statements.TryCatch> activity in which the <xref:System.IO.TextWriter> variable is declared, to ensure that it runs even if an exception should occur during execution of the Try block.</span></span>  
  
 <span data-ttu-id="e2b14-115">Можно ввести в `exit` для экземпляра рабочего процесса завершения работы программы.</span><span class="sxs-lookup"><span data-stu-id="e2b14-115">You can type in `exit` to complete the workflow instance and exit the program.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="e2b14-116">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e2b14-116">To run the sample</span></span>  
  
1.  <span data-ttu-id="e2b14-117">Откройте решение NoPersistZone.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2b14-117">Open the NoPersistZone.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="e2b14-118">Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="e2b14-118">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="e2b14-119">После успешного построения нажмите клавишу F5 или выберите **начать отладку** из **отладки** меню или нажмите клавиши CTRL + F5 или выберите **Запуск без отладки** из **Отладки** меню для запуска без отладки.</span><span class="sxs-lookup"><span data-stu-id="e2b14-119">Once the build has succeeded, press F5 or select **Start Debugging** from the **Debug** menu alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="e2b14-120">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e2b14-120">To cleanup (optional)</span></span>  
  
1.  <span data-ttu-id="e2b14-121">Для удаления хранилища экземпляров SQL запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="e2b14-121">To remove the SQL Instance Store, run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2b14-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e2b14-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e2b14-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e2b14-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e2b14-124">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2b14-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e2b14-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e2b14-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`  
  
## <a name="see-also"></a><span data-ttu-id="e2b14-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e2b14-126">See Also</span></span>
