---
title: Практическое руководство. Создание и запуск длительного рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: fd7bf92750c6e314a5c9105bb961bf68b68182cb
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063824"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="7d8db-102">Практическое руководство. Создание и запуск длительного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-102">How to: Create and Run a Long Running Workflow</span></span>
<span data-ttu-id="7d8db-103">Одна из функций центра Windows Workflow Foundation (WF) предоставляет возможность среды выполнения сохранения и выгрузки бездействующих рабочих процессов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7d8db-103">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="7d8db-104">Действия, описанные в [как: Запуск рабочего процесса](how-to-run-a-workflow.md) показаны основы размещение рабочих процессов, используя консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="7d8db-104">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="7d8db-105">Приведены примеры запуска рабочих процессов, обработчиков жизненного цикла рабочего процесса и возобновления закладок.</span><span class="sxs-lookup"><span data-stu-id="7d8db-105">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="7d8db-106">Для эффективной демонстрации сохранения рабочего процесса требуется более сложный узел рабочих процессов, обеспечивающий запуск и возобновление нескольких экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-106">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="7d8db-107">На этом шаге учебника показано, как создать ведущее приложение форм Windows Form, которое обеспечивает запуск и возобновление нескольких экземпляров рабочих процессов, сохранение рабочего процесса и основу для таких дополнительных возможностей, как отслеживание версий, которые показаны в последующих шагах учебника, и управление ими.</span><span class="sxs-lookup"><span data-stu-id="7d8db-107">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d8db-108">Этот шаг руководства и последующие шаги использовать все три типа рабочего процесса из [как: Создание рабочего процесса](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="7d8db-108">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="7d8db-109">Если вы не прошли все три типа можно загрузить полную версию из учебника [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="7d8db-109">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d8db-110">Чтобы скачать полную версию или просмотреть пошаговое видео учебника, см. в разделе [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="7d8db-110">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="7d8db-111">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="7d8db-111">In this topic</span></span>  
  
- [<span data-ttu-id="7d8db-112">Чтобы создать базу данных сохраняемости</span><span class="sxs-lookup"><span data-stu-id="7d8db-112">To create the persistence database</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreatePersistenceDatabase)  
  
- [<span data-ttu-id="7d8db-113">Для добавления ссылки на сборки DurableInstancing</span><span class="sxs-lookup"><span data-stu-id="7d8db-113">To add the reference to the DurableInstancing assemblies</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddReference)  
  
- [<span data-ttu-id="7d8db-114">Создание ведущей формы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-114">To create the workflow host form</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreateForm)  
  
- [<span data-ttu-id="7d8db-115">Для добавления свойств и вспомогательных методов формы</span><span class="sxs-lookup"><span data-stu-id="7d8db-115">To add the properties and helper methods of the form</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods)  
  
- [<span data-ttu-id="7d8db-116">Чтобы настроить хранилище экземпляров, обработчиков жизненного цикла рабочего процесса и расширения</span><span class="sxs-lookup"><span data-stu-id="7d8db-116">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_ConfigureWorkflowApplication)  
  
- [<span data-ttu-id="7d8db-117">Чтобы включить запуск и возобновление нескольких типов рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7d8db-117">To enable starting and resuming multiple workflow types</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_WorkflowVersionMap)  
  
- [<span data-ttu-id="7d8db-118">Чтобы запустить новый рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="7d8db-118">To start a new workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_StartWorkflow)  
  
- [<span data-ttu-id="7d8db-119">Возобновление рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-119">To resume a workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_ResumeWorkflow)  
  
- [<span data-ttu-id="7d8db-120">Завершение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-120">To terminate a workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_TerminateWorkflow)  
  
- [<span data-ttu-id="7d8db-121">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="7d8db-121">To build and run the application</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_BuildAndRun)  
  
### <a name="BKMK_CreatePersistenceDatabase"></a> <span data-ttu-id="7d8db-122">Чтобы создать базу данных сохраняемости</span><span class="sxs-lookup"><span data-stu-id="7d8db-122">To create the persistence database</span></span>  
  
1. <span data-ttu-id="7d8db-123">Откройте SQL Server Management Studio и подключитесь к локальному серверу, например **. \SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-123">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="7d8db-124">Щелкните правой кнопкой мыши **баз данных** узла на локальном сервере, а затем выберите **новую базу данных**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-124">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="7d8db-125">Присвойте имя новой базы данных **WF45GettingStartedTutorial**, примите все остальные значения, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-125">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7d8db-126">Убедитесь, что у вас есть **Create Database** разрешение на локальном сервере, перед созданием базы данных.</span><span class="sxs-lookup"><span data-stu-id="7d8db-126">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>  
  
2. <span data-ttu-id="7d8db-127">Выберите **откройте**, **файл** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="7d8db-127">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="7d8db-128">Перейдите в следующую папку: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="7d8db-128">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span></span>  
  
     <span data-ttu-id="7d8db-129">Выберите следующие два файла и нажмите кнопку **откройте**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-129">Select the following two files and click **Open**.</span></span>  
  
    - <span data-ttu-id="7d8db-130">SqlWorkflowInstanceStoreLogic.sql</span><span class="sxs-lookup"><span data-stu-id="7d8db-130">SqlWorkflowInstanceStoreLogic.sql</span></span>  
  
    - <span data-ttu-id="7d8db-131">SqlWorkflowInstanceStoreSchema.sql</span><span class="sxs-lookup"><span data-stu-id="7d8db-131">SqlWorkflowInstanceStoreSchema.sql</span></span>  
  
3. <span data-ttu-id="7d8db-132">Выберите **SqlWorkflowInstanceStoreSchema.sql** из **окно** меню.</span><span class="sxs-lookup"><span data-stu-id="7d8db-132">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="7d8db-133">Убедитесь, что **WF45GettingStartedTutorial** выбран в **доступных баз данных** раскрывающегося списка и выберите **Execute** из **запроса**меню.</span><span class="sxs-lookup"><span data-stu-id="7d8db-133">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>  
  
4. <span data-ttu-id="7d8db-134">Выберите **SqlWorkflowInstanceStoreLogic.sql** из **окно** меню.</span><span class="sxs-lookup"><span data-stu-id="7d8db-134">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="7d8db-135">Убедитесь, что **WF45GettingStartedTutorial** выбран в **доступных баз данных** раскрывающегося списка и выберите **Execute** из **запроса**меню.</span><span class="sxs-lookup"><span data-stu-id="7d8db-135">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="7d8db-136">Важно выполнить предыдущие два шага в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="7d8db-136">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="7d8db-137">Если выполнить запросы в неправильном порядке, произойдет ошибка и база данных сохраняемости не будет правильно настроена.</span><span class="sxs-lookup"><span data-stu-id="7d8db-137">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>  
  
### <a name="BKMK_AddReference"></a> <span data-ttu-id="7d8db-138">Для добавления ссылки на сборки DurableInstancing</span><span class="sxs-lookup"><span data-stu-id="7d8db-138">To add the reference to the DurableInstancing assemblies</span></span>  
  
1. <span data-ttu-id="7d8db-139">Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-139">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="7d8db-140">Выберите **сборки** из **добавить ссылку** списка и введите `DurableInstancing` в **поиск сборок** поле.</span><span class="sxs-lookup"><span data-stu-id="7d8db-140">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="7d8db-141">Сборки отфильтруются, и будет легче выбрать необходимые ссылки.</span><span class="sxs-lookup"><span data-stu-id="7d8db-141">This filters the assemblies and makes the desired references easier to select.</span></span>  
  
3. <span data-ttu-id="7d8db-142">Установите флажок рядом с **System.Activities.DurableInstancing** и **System.Runtime.DurableInstancing** из **результаты поиска** , а нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-142">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>  
  
### <a name="BKMK_CreateForm"></a> <span data-ttu-id="7d8db-143">Создание ведущей формы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-143">To create the workflow host form</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d8db-144">В шагах этой процедуры показано, как добавить и настроить форму вручную.</span><span class="sxs-lookup"><span data-stu-id="7d8db-144">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="7d8db-145">При необходимости можно загрузить файлы решений для учебника и добавить готовую форму в проект.</span><span class="sxs-lookup"><span data-stu-id="7d8db-145">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="7d8db-146">Чтобы скачать файлы учебника, см. в разделе [Windows Workflow Foundation (WF45) - Приступая к работе](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="7d8db-146">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="7d8db-147">После загрузки файлов, щелкните правой кнопкой мыши **NumberGuessWorkflowHost** и выберите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-147">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="7d8db-148">Добавьте ссылку на **System.Windows.Forms** и **System.Drawing**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-148">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="7d8db-149">Эти ссылки добавляются автоматически при добавлении новой формы из **добавить**, **новый элемент** меню, но необходимо добавить вручную при импорте формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-149">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="7d8db-150">После добавления ссылок щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **добавить**, **существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-150">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="7d8db-151">Перейдите к `Form` папке в файлах проекта, выберите **WorkflowHostForm.cs** (или **WorkflowHostForm.vb**) и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-151">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="7d8db-152">Если вы решили импортировать форму, а затем переходите к следующему разделу, [для добавления свойств и вспомогательных методов формы](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).</span><span class="sxs-lookup"><span data-stu-id="7d8db-152">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).</span></span>  
  
1. <span data-ttu-id="7d8db-153">Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **добавить**, **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-153">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="7d8db-154">В **установленные** шаблонов выберите **формы Windows**, тип `WorkflowHostForm` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-154">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>  
  
3. <span data-ttu-id="7d8db-155">Задайте следующие свойства формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-155">Configure the following properties on the form.</span></span>  
  
    |<span data-ttu-id="7d8db-156">Свойство</span><span class="sxs-lookup"><span data-stu-id="7d8db-156">Property</span></span>|<span data-ttu-id="7d8db-157">Значение</span><span class="sxs-lookup"><span data-stu-id="7d8db-157">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="7d8db-158">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="7d8db-158">FormBorderStyle</span></span>|<span data-ttu-id="7d8db-159">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="7d8db-159">FixedSingle</span></span>|  
    |<span data-ttu-id="7d8db-160">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="7d8db-160">MaximizeBox</span></span>|<span data-ttu-id="7d8db-161">False</span><span class="sxs-lookup"><span data-stu-id="7d8db-161">False</span></span>|  
    |<span data-ttu-id="7d8db-162">Размер</span><span class="sxs-lookup"><span data-stu-id="7d8db-162">Size</span></span>|<span data-ttu-id="7d8db-163">400, 420</span><span class="sxs-lookup"><span data-stu-id="7d8db-163">400, 420</span></span>|  
  
4. <span data-ttu-id="7d8db-164">Добавьте в форму следующие элементы управления в указанном порядке и задайте значения свойств.</span><span class="sxs-lookup"><span data-stu-id="7d8db-164">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>  
  
    |<span data-ttu-id="7d8db-165">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="7d8db-165">Control</span></span>|<span data-ttu-id="7d8db-166">Свойство: Значение</span><span class="sxs-lookup"><span data-stu-id="7d8db-166">Property: Value</span></span>|  
    |-------------|---------------------|  
    |<span data-ttu-id="7d8db-167">**Button**</span><span class="sxs-lookup"><span data-stu-id="7d8db-167">**Button**</span></span>|<span data-ttu-id="7d8db-168">Имя. NewGame</span><span class="sxs-lookup"><span data-stu-id="7d8db-168">Name: NewGame</span></span><br /><br /> <span data-ttu-id="7d8db-169">Расположение: 13, 13</span><span class="sxs-lookup"><span data-stu-id="7d8db-169">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="7d8db-170">Размер: 75, 23</span><span class="sxs-lookup"><span data-stu-id="7d8db-170">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="7d8db-171">Text: Новая игра</span><span class="sxs-lookup"><span data-stu-id="7d8db-171">Text: New Game</span></span>|  
    |<span data-ttu-id="7d8db-172">**Label**</span><span class="sxs-lookup"><span data-stu-id="7d8db-172">**Label**</span></span>|<span data-ttu-id="7d8db-173">Расположение: 94, 18</span><span class="sxs-lookup"><span data-stu-id="7d8db-173">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="7d8db-174">Text: Угадайте число от 1 до</span><span class="sxs-lookup"><span data-stu-id="7d8db-174">Text: Guess a number from 1 to</span></span>|  
    |<span data-ttu-id="7d8db-175">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="7d8db-175">**ComboBox**</span></span>|<span data-ttu-id="7d8db-176">Имя. NumberRange</span><span class="sxs-lookup"><span data-stu-id="7d8db-176">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="7d8db-177">Значением DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="7d8db-177">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="7d8db-178">Элементы: 10, 100, 1000</span><span class="sxs-lookup"><span data-stu-id="7d8db-178">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="7d8db-179">Расположение: 228, 12</span><span class="sxs-lookup"><span data-stu-id="7d8db-179">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="7d8db-180">Размер: 143, 21</span><span class="sxs-lookup"><span data-stu-id="7d8db-180">Size: 143, 21</span></span>|  
    |<span data-ttu-id="7d8db-181">**Label**</span><span class="sxs-lookup"><span data-stu-id="7d8db-181">**Label**</span></span>|<span data-ttu-id="7d8db-182">Расположение: 13, 43</span><span class="sxs-lookup"><span data-stu-id="7d8db-182">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="7d8db-183">Text: Тип рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-183">Text: Workflow type</span></span>|  
    |<span data-ttu-id="7d8db-184">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="7d8db-184">**ComboBox**</span></span>|<span data-ttu-id="7d8db-185">Имя. WorkflowType</span><span class="sxs-lookup"><span data-stu-id="7d8db-185">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="7d8db-186">Значением DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="7d8db-186">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="7d8db-187">Элементы: StateMachineNumberGuessWorkflow FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="7d8db-187">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="7d8db-188">Расположение: 94, 40</span><span class="sxs-lookup"><span data-stu-id="7d8db-188">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="7d8db-189">Размер: 277, 21</span><span class="sxs-lookup"><span data-stu-id="7d8db-189">Size: 277, 21</span></span>|  
    |<span data-ttu-id="7d8db-190">**Label**</span><span class="sxs-lookup"><span data-stu-id="7d8db-190">**Label**</span></span>|<span data-ttu-id="7d8db-191">Имя. WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="7d8db-191">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="7d8db-192">Расположение: 13, 362</span><span class="sxs-lookup"><span data-stu-id="7d8db-192">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="7d8db-193">Text: Версия рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-193">Text: Workflow version</span></span>|  
    |<span data-ttu-id="7d8db-194">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="7d8db-194">**GroupBox**</span></span>|<span data-ttu-id="7d8db-195">Расположение: 13, 67</span><span class="sxs-lookup"><span data-stu-id="7d8db-195">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="7d8db-196">Размер: 358, 287</span><span class="sxs-lookup"><span data-stu-id="7d8db-196">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="7d8db-197">Text: Игра</span><span class="sxs-lookup"><span data-stu-id="7d8db-197">Text: Game</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="7d8db-198">При добавлении следующих элементов управления, их следует поместите в GroupBox.</span><span class="sxs-lookup"><span data-stu-id="7d8db-198">When adding the following controls, put them into the GroupBox.</span></span>  
  
    |<span data-ttu-id="7d8db-199">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="7d8db-199">Control</span></span>|<span data-ttu-id="7d8db-200">Свойство: Значение</span><span class="sxs-lookup"><span data-stu-id="7d8db-200">Property: Value</span></span>|  
    |-------------|---------------------|  
    |<span data-ttu-id="7d8db-201">**Label**</span><span class="sxs-lookup"><span data-stu-id="7d8db-201">**Label**</span></span>|<span data-ttu-id="7d8db-202">Расположение: 7, 20</span><span class="sxs-lookup"><span data-stu-id="7d8db-202">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="7d8db-203">Text: Идентификатор экземпляра рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-203">Text: Workflow Instance Id</span></span>|  
    |<span data-ttu-id="7d8db-204">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="7d8db-204">**ComboBox**</span></span>|<span data-ttu-id="7d8db-205">Имя. InstanceId</span><span class="sxs-lookup"><span data-stu-id="7d8db-205">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="7d8db-206">Значением DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="7d8db-206">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="7d8db-207">Расположение: 121, 17</span><span class="sxs-lookup"><span data-stu-id="7d8db-207">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="7d8db-208">Размер: 227, 21</span><span class="sxs-lookup"><span data-stu-id="7d8db-208">Size: 227, 21</span></span>|  
    |<span data-ttu-id="7d8db-209">**Label**</span><span class="sxs-lookup"><span data-stu-id="7d8db-209">**Label**</span></span>|<span data-ttu-id="7d8db-210">Расположение: 7, 47</span><span class="sxs-lookup"><span data-stu-id="7d8db-210">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="7d8db-211">Text: Догадка</span><span class="sxs-lookup"><span data-stu-id="7d8db-211">Text: Guess</span></span>|  
    |<span data-ttu-id="7d8db-212">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="7d8db-212">**TextBox**</span></span>|<span data-ttu-id="7d8db-213">Имя. Догадка</span><span class="sxs-lookup"><span data-stu-id="7d8db-213">Name: Guess</span></span><br /><br /> <span data-ttu-id="7d8db-214">Расположение: 50, 44</span><span class="sxs-lookup"><span data-stu-id="7d8db-214">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="7d8db-215">Размер: 65, 20</span><span class="sxs-lookup"><span data-stu-id="7d8db-215">Size: 65, 20</span></span>|  
    |<span data-ttu-id="7d8db-216">**Button**</span><span class="sxs-lookup"><span data-stu-id="7d8db-216">**Button**</span></span>|<span data-ttu-id="7d8db-217">Имя. EnterGuess</span><span class="sxs-lookup"><span data-stu-id="7d8db-217">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="7d8db-218">Расположение: 121, 42</span><span class="sxs-lookup"><span data-stu-id="7d8db-218">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="7d8db-219">Размер: 75, 23</span><span class="sxs-lookup"><span data-stu-id="7d8db-219">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="7d8db-220">Text: Ввести догадку</span><span class="sxs-lookup"><span data-stu-id="7d8db-220">Text: Enter Guess</span></span>|  
    |<span data-ttu-id="7d8db-221">**Button**</span><span class="sxs-lookup"><span data-stu-id="7d8db-221">**Button**</span></span>|<span data-ttu-id="7d8db-222">Имя. QuitGame</span><span class="sxs-lookup"><span data-stu-id="7d8db-222">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="7d8db-223">Расположение: 274, 42</span><span class="sxs-lookup"><span data-stu-id="7d8db-223">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="7d8db-224">Размер: 75, 23</span><span class="sxs-lookup"><span data-stu-id="7d8db-224">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="7d8db-225">Text: Выход</span><span class="sxs-lookup"><span data-stu-id="7d8db-225">Text: Quit</span></span>|  
    |<span data-ttu-id="7d8db-226">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="7d8db-226">**TextBox**</span></span>|<span data-ttu-id="7d8db-227">Имя. WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="7d8db-227">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="7d8db-228">Расположение: 10, 73</span><span class="sxs-lookup"><span data-stu-id="7d8db-228">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="7d8db-229">Многострочный: True</span><span class="sxs-lookup"><span data-stu-id="7d8db-229">Multiline: True</span></span><br /><br /> <span data-ttu-id="7d8db-230">Только для чтения: True</span><span class="sxs-lookup"><span data-stu-id="7d8db-230">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="7d8db-231">Полосы прокрутки: Вертикально</span><span class="sxs-lookup"><span data-stu-id="7d8db-231">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="7d8db-232">Размер: 338, 208</span><span class="sxs-lookup"><span data-stu-id="7d8db-232">Size: 338, 208</span></span>|  
  
5. <span data-ttu-id="7d8db-233">Задайте **AcceptButton** свойства формы **EnterGuess**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-233">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>  
  
 <span data-ttu-id="7d8db-234">В следующем примере показана заполненная форма.</span><span class="sxs-lookup"><span data-stu-id="7d8db-234">The following example illustrates the completed form.</span></span>  
  
 ![Снимок экрана формы узла рабочего процесса Windows Workflow Foundation.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)  
  
### <a name="BKMK_AddHelperMethods"></a> <span data-ttu-id="7d8db-236">Для добавления свойств и вспомогательных методов формы</span><span class="sxs-lookup"><span data-stu-id="7d8db-236">To add the properties and helper methods of the form</span></span>  
 <span data-ttu-id="7d8db-237">В этом разделе показано, как добавить в класс формы свойства и вспомогательные методы, которые настраивают пользовательский интерфейс формы для запуска и возобновления рабочих процессов угадывания числа.</span><span class="sxs-lookup"><span data-stu-id="7d8db-237">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>  
  
1. <span data-ttu-id="7d8db-238">Щелкните правой кнопкой мыши **WorkflowHostForm** в **обозревателе решений** и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-238">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="7d8db-239">Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).</span><span class="sxs-lookup"><span data-stu-id="7d8db-239">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Windows.Forms  
    Imports System.Activities.DurableInstancing  
    Imports System.Activities  
    Imports System.Data.SqlClient  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    using System.Activities.DurableInstancing;  
    using System.Activities;  
    using System.Data.SqlClient;  
    using System.IO;  
    ```  
  
3. <span data-ttu-id="7d8db-240">Добавьте следующие объявления элементов в **WorkflowHostForm** класса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-240">Add the following member declarations to the **WorkflowHostForm** class.</span></span>  
  
    ```vb  
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"  
    Dim store As SqlWorkflowInstanceStore  
    Dim WorkflowStarting As Boolean  
    ```  
  
    ```csharp  
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";  
    SqlWorkflowInstanceStore store;  
    bool WorkflowStarting;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="7d8db-241">Если у вас другая строка подключения, обновите строку `connectionString` так, чтобы она указывала на вашу базу данных.</span><span class="sxs-lookup"><span data-stu-id="7d8db-241">If your connection string is different, update `connectionString` to refer to your database.</span></span>  
  
4. <span data-ttu-id="7d8db-242">Добавьте свойство `WorkflowInstanceId` в класс `WorkflowFormHost`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-242">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>  
  
    ```vb  
    Public ReadOnly Property WorkflowInstanceId() As Guid  
        Get  
            If InstanceId.SelectedIndex = -1 Then  
                Return Guid.Empty  
            Else  
                Return New Guid(InstanceId.SelectedItem.ToString())  
            End If  
        End Get  
    End Property  
    ```  
  
    ```csharp  
    public Guid WorkflowInstanceId  
    {  
        get  
        {  
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;  
        }  
    }  
    ```  
  
     <span data-ttu-id="7d8db-243">`InstanceId` Поле со списком отображает список идентификаторов экземпляра сохраненного рабочего процесса и `WorkflowInstanceId` свойство возвращает текущий выбранный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="7d8db-243">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>  
  
5. <span data-ttu-id="7d8db-244">Добавьте обработчик события `Load` формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-244">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="7d8db-245">Чтобы добавить обработчик, перейдите в **конструкторе** формы, щелкните **события** значок в верхней части **свойства** окна и дважды щелкните **нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-245">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>  
  
    ```vb  
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load  
  
    End Sub  
    ```  
  
    ```csharp  
    private void WorkflowHostForm_Load(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
6. <span data-ttu-id="7d8db-246">Добавьте следующий код к `WorkflowHostForm_Load`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-246">Add the following code to `WorkflowHostForm_Load`.</span></span>  
  
    ```vb  
    'Initialize the store and configure it so that it can be used for  
    'multiple WorkflowApplication instances.  
    store = New SqlWorkflowInstanceStore(connectionString)  
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)  
  
    'Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0  
    WorkflowType.SelectedIndex = 0  
  
    ListPersistedWorkflows()  
    ```  
  
    ```csharp  
    // Initialize the store and configure it so that it can be used for  
    // multiple WorkflowApplication instances.  
    store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);  
  
    // Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0;  
    WorkflowType.SelectedIndex = 0;  
  
    ListPersistedWorkflows();  
    ```  
  
     <span data-ttu-id="7d8db-247">Когда форма загружена, настраивается класс `SqlWorkflowInstanceStore`, для полей со списком диапазонов и типов рабочего процесса устанавливаются значения по умолчанию, а сохраненные экземпляры рабочих процессов добавляются в поле `InstanceId`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-247">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>  
  
7. <span data-ttu-id="7d8db-248">Добавьте обработчик событий `SelectedIndexChanged` для `InstanceId`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-248">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="7d8db-249">Чтобы добавить обработчик, перейдите в **конструкторе** формы, выберите `InstanceId` поле со списком, нажмите кнопку **события** значок в верхней части **свойства** окно, и Дважды щелкните **SelectedIndexChanged**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-249">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
8. <span data-ttu-id="7d8db-250">Добавьте следующий код к `InstanceId_SelectedIndexChanged`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-250">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="7d8db-251">Каждый раз, когда пользователь выбирает рабочий процесс с помощью поля со списком, этот обработчик обновляет окно состояния.</span><span class="sxs-lookup"><span data-stu-id="7d8db-251">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>  
  
    ```vb  
    If InstanceId.SelectedIndex = -1 Then  
        Return  
    End If  
  
    'Clear the status window.  
    WorkflowStatus.Clear()  
  
    'Get the workflow version and display it.  
    'If the workflow is just starting then this info will not  
    'be available in the persistence store so do not try and retrieve it.  
    If Not WorkflowStarting Then  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        WorkflowVersion.Text = _  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
        'Unload the instance.  
        instance.Abandon()  
    End If  
    ```  
  
    ```csharp  
    if (InstanceId.SelectedIndex == -1)  
    {  
        return;  
    }  
  
    // Clear the status window.  
    WorkflowStatus.Clear();  
  
    // Get the workflow version and display it.  
    // If the workflow is just starting then this info will not  
    // be available in the persistence store so do not try and retrieve it.  
    if (!WorkflowStarting)  
    {  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
        WorkflowVersion.Text =  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
        // Unload the instance.  
        instance.Abandon();  
    }  
    ```  
  
9. <span data-ttu-id="7d8db-252">Добавьте следующий метод `ListPersistedWorkflows` в класс формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-252">Add the following `ListPersistedWorkflows` method to the form class.</span></span>  
  
    ```vb  
    Private Sub ListPersistedWorkflows()  
        Using localCon As New SqlConnection(connectionString)  
            Dim localCmd As String = _  
                "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]"  
  
            Dim cmd As SqlCommand = localCon.CreateCommand()  
            cmd.CommandText = localCmd  
            localCon.Open()  
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
  
                While (reader.Read())  
                    'Get the InstanceId of the persisted Workflow.  
                    Dim id As Guid = Guid.Parse(reader(0).ToString())  
                    InstanceId.Items.Add(id)  
                End While  
            End Using  
        End Using  
    End Sub  
    ```  
  
    ```csharp  
    using (SqlConnection localCon = new SqlConnection(connectionString))  
    {  
        string localCmd =  
            "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]";  
  
        SqlCommand cmd = localCon.CreateCommand();  
        cmd.CommandText = localCmd;  
        localCon.Open();  
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))  
        {  
            while (reader.Read())  
            {  
                // Get the InstanceId of the persisted Workflow  
                Guid id = Guid.Parse(reader[0].ToString());  
                InstanceId.Items.Add(id);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="7d8db-253">`ListPersistedWorkflows` запрашивает у хранилища экземпляров сохраненные экземпляры рабочих процессов и добавляет их идентификаторы в поле со списком `cboInstanceId`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-253">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>  
  
10. <span data-ttu-id="7d8db-254">Добавьте следующий метод `UpdateStatus` и соответствующий делегат в класс формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-254">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="7d8db-255">Этот метод обновляет окно состояния в форме с данными о состоянии рабочего процесса, выполняемого в данный момент.</span><span class="sxs-lookup"><span data-stu-id="7d8db-255">This method updates the status window on the form with the status of the currently running workflow.</span></span>  
  
    ```vb  
    Private Delegate Sub UpdateStatusDelegate(msg As String)  
    Public Sub UpdateStatus(msg As String)  
        'We may be on a different thread so we need to  
        'make this call using BeginInvoke.  
        If InvokeRequired Then  
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)  
        Else  
            If Not msg.EndsWith(vbCrLf) Then  
                msg = msg & vbCrLf  
            End If  
  
            WorkflowStatus.AppendText(msg)  
  
            'Ensure that the newly added status is visible.  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length  
            WorkflowStatus.ScrollToCaret()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void UpdateStatusDelegate(string msg);  
    public void UpdateStatus(string msg)  
    {  
        // We may be on a different thread so we need to  
        // make this call using BeginInvoke.  
        if (InvokeRequired)  
        {  
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);  
        }  
        else  
        {  
            if (!msg.EndsWith("\r\n"))  
            {  
                msg += "\r\n";  
            }  
            WorkflowStatus.AppendText(msg);  
  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;  
            WorkflowStatus.ScrollToCaret();  
        }  
    }  
    ```  
  
11. <span data-ttu-id="7d8db-256">Добавьте следующий метод `GameOver` и соответствующий делегат в класс формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-256">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="7d8db-257">После завершения рабочего процесса, этот метод обновляет пользовательский Интерфейс формы, удаляя идентификатор экземпляра завершенного рабочего процесса из **InstanceId** поле со списком.</span><span class="sxs-lookup"><span data-stu-id="7d8db-257">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>  
  
    ```vb  
    Private Delegate Sub GameOverDelegate()  
    Private Sub GameOver()  
        If InvokeRequired Then  
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))  
        Else  
            'Remove this instance from the InstanceId combo box.  
            InstanceId.Items.Remove(InstanceId.SelectedItem)  
            InstanceId.SelectedIndex = -1  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void GameOverDelegate();  
    private void GameOver()  
    {  
        if (InvokeRequired)  
        {  
            BeginInvoke(new GameOverDelegate(GameOver));  
        }  
        else  
        {  
            // Remove this instance from the combo box  
            InstanceId.Items.Remove(InstanceId.SelectedItem);  
            InstanceId.SelectedIndex = -1;  
        }  
    }  
    ```  
  
### <a name="BKMK_ConfigureWorkflowApplication"></a> <span data-ttu-id="7d8db-258">Чтобы настроить хранилище экземпляров, обработчиков жизненного цикла рабочего процесса и расширения</span><span class="sxs-lookup"><span data-stu-id="7d8db-258">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>  
  
1. <span data-ttu-id="7d8db-259">Добавьте метод `ConfigureWorkflowApplication` в класс формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-259">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {      
    }  
    ```  
  
     <span data-ttu-id="7d8db-260">Этот метод задает `WorkflowApplication`, добавляет необходимые расширения и обработчики событий жизненного цикла рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-260">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>  
  
2. <span data-ttu-id="7d8db-261">В `ConfigureWorkflowApplication` укажите `SqlWorkflowInstanceStore` для `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-261">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>  
  
    ```vb  
    'Configure the persistence store.  
    wfApp.InstanceStore = store  
    ```  
  
    ```csharp  
    // Configure the persistence store.  
    wfApp.InstanceStore = store;  
    ```  
  
3. <span data-ttu-id="7d8db-262">Затем создайте экземпляр класса `StringWriter` и добавьте его в коллекцию `Extensions` приложения `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-262">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="7d8db-263">Когда `StringWriter` добавляется к расширениям, он записывает все `WriteLine` выходные данные действия.</span><span class="sxs-lookup"><span data-stu-id="7d8db-263">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="7d8db-264">Когда рабочий процесс становится неактивным, выходные данные `WriteLine` можно извлечь из `StringWriter` и показать на форме.</span><span class="sxs-lookup"><span data-stu-id="7d8db-264">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>  
  
    ```vb  
    'Add a StringWriter to the extensions. This captures the output  
    'from the WriteLine activities so we can display it in the form.  
    Dim sw As New StringWriter()  
    wfApp.Extensions.Add(sw)  
    ```  
  
    ```csharp  
    // Add a StringWriter to the extensions. This captures the output  
    // from the WriteLine activities so we can display it in the form.  
    StringWriter sw = new StringWriter();  
    wfApp.Extensions.Add(sw);  
    ```  
  
4. <span data-ttu-id="7d8db-265">Добавьте следующий обработчик события `Completed`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-265">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="7d8db-266">После успешного завершения рабочего процесса число ходов, которое потребовалось для угадывания числа, отображается в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="7d8db-266">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="7d8db-267">Если рабочий процесс завершается, выдаются сведения об исключении, которое явилось причиной.</span><span class="sxs-lookup"><span data-stu-id="7d8db-267">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="7d8db-268">В конце обработчика вызывается метод `GameOver`, который удаляет завершенный рабочий процесс из списка рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="7d8db-268">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>  
  
    ```vb  
    wfApp.Completed = _  
        Sub(e As WorkflowApplicationCompletedEventArgs)  
            If e.CompletionState = ActivityInstanceState.Faulted Then  
                UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                    e.TerminationException.GetType().FullName, _  
                    e.TerminationException.Message))  
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                UpdateStatus("Workflow Canceled.")  
            Else  
                Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
            End If  
            GameOver()  
        End Sub  
    ```  
  
    ```csharp  
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
    {  
        if (e.CompletionState == ActivityInstanceState.Faulted)  
        {  
            UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                e.TerminationException.GetType().FullName,  
                e.TerminationException.Message));  
        }  
        else if (e.CompletionState == ActivityInstanceState.Canceled)  
        {  
            UpdateStatus("Workflow Canceled.");  
        }  
        else  
        {  
            int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
            UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
        }  
        GameOver();  
    };  
    ```  
  
5. <span data-ttu-id="7d8db-269">Добавьте следующие обработчики `Aborted` и `OnUnhandledException`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-269">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="7d8db-270">Метод `GameOver` не вызывается из обработчика `Aborted`, поскольку в случае аварийного завершения выполнения экземпляра рабочего процесса работа экземпляра не прекращается окончательно, позже можно перезапустить экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7d8db-270">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>  
  
    ```vb  
    wfApp.Aborted = _  
        Sub(e As WorkflowApplicationAbortedEventArgs)  
            UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                e.Reason.GetType().FullName, _  
                e.Reason.Message))  
        End Sub  
  
    wfApp.OnUnhandledException = _  
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
            UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                e.UnhandledException.GetType().FullName, _  
                e.UnhandledException.Message))  
            GameOver()  
            Return UnhandledExceptionAction.Terminate  
        End Function  
    ```  
  
    ```csharp  
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
    {  
        UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                e.Reason.GetType().FullName,  
                e.Reason.Message));  
    };  
  
    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
    {  
        UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                e.UnhandledException.GetType().FullName,  
                e.UnhandledException.Message));  
        GameOver();  
        return UnhandledExceptionAction.Terminate;  
    };  
    ```  
  
6. <span data-ttu-id="7d8db-271">Добавьте следующий обработчик `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-271">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="7d8db-272">Этот обработчик получает расширение `StringWriter`, которое было добавлено, извлекает данные из действий `WriteLine` и отображает их в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="7d8db-272">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>  
  
    ```vb  
    wfApp.PersistableIdle = _  
        Function(e As WorkflowApplicationIdleEventArgs)  
            'Send the current WriteLine outputs to the status window.  
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
            For Each writer In writers  
                UpdateStatus(writer.ToString())  
            Next  
            Return PersistableIdleAction.Unload  
        End Function  
    ```  
  
    ```csharp  
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
    {  
        // Send the current WriteLine outputs to the status window.  
        var writers = e.GetInstanceExtensions<StringWriter>();  
        foreach (var writer in writers)  
        {  
            UpdateStatus(writer.ToString());  
        }  
        return PersistableIdleAction.Unload;  
    };  
    ```  
  
     <span data-ttu-id="7d8db-273">Для перечисления <xref:System.Activities.PersistableIdleAction> существует три значения: <xref:System.Activities.PersistableIdleAction.None>,<xref:System.Activities.PersistableIdleAction.Persist> и <xref:System.Activities.PersistableIdleAction.Unload>.</span><span class="sxs-lookup"><span data-stu-id="7d8db-273">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="7d8db-274">Значение <xref:System.Activities.PersistableIdleAction.Persist> вызывает сохранение рабочего процесса, но не его выгрузку.</span><span class="sxs-lookup"><span data-stu-id="7d8db-274"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="7d8db-275">Значение <xref:System.Activities.PersistableIdleAction.Unload> вызывает сохранение и выгрузку рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-275"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>  
  
     <span data-ttu-id="7d8db-276">Ниже приведен полный пример метода `ConfigureWorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-276">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        wfApp.Completed = _  
            Sub(e As WorkflowApplicationCompletedEventArgs)  
                If e.CompletionState = ActivityInstanceState.Faulted Then  
                    UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                        e.TerminationException.GetType().FullName, _  
                        e.TerminationException.Message))  
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                    UpdateStatus("Workflow Canceled.")  
                Else  
                    Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                    UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
                End If  
                GameOver()  
            End Sub  
  
        wfApp.Aborted = _  
            Sub(e As WorkflowApplicationAbortedEventArgs)  
                UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                    e.Reason.GetType().FullName, _  
                    e.Reason.Message))  
            End Sub  
  
        wfApp.OnUnhandledException = _  
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
                UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                    e.UnhandledException.GetType().FullName, _  
                    e.UnhandledException.Message))  
                GameOver()  
                Return UnhandledExceptionAction.Terminate  
            End Function  
  
        wfApp.PersistableIdle = _  
            Function(e As WorkflowApplicationIdleEventArgs)  
                'Send the current WriteLine outputs to the status window.  
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
                For Each writer In writers  
                    UpdateStatus(writer.ToString())  
                Next  
                Return PersistableIdleAction.Unload  
            End Function  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
        {  
            if (e.CompletionState == ActivityInstanceState.Faulted)  
            {  
                UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                    e.TerminationException.GetType().FullName,  
                    e.TerminationException.Message));  
            }  
            else if (e.CompletionState == ActivityInstanceState.Canceled)  
            {  
                UpdateStatus("Workflow Canceled.");  
            }  
            else  
            {  
                int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
                UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
            }  
            GameOver();  
        };  
  
        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
        {  
            UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                    e.Reason.GetType().FullName,  
                    e.Reason.Message));  
        };  
  
        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                    e.UnhandledException.GetType().FullName,  
                    e.UnhandledException.Message));  
            GameOver();  
            return UnhandledExceptionAction.Terminate;  
        };  
  
        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
        {  
            // Send the current WriteLine outputs to the status window.  
            var writers = e.GetInstanceExtensions<StringWriter>();  
            foreach (var writer in writers)  
            {  
                UpdateStatus(writer.ToString());  
            }  
            return PersistableIdleAction.Unload;  
        };  
    }  
    ```  
  
### <a name="BKMK_WorkflowVersionMap"></a> <span data-ttu-id="7d8db-277">Чтобы включить запуск и возобновление нескольких типов рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7d8db-277">To enable starting and resuming multiple workflow types</span></span>  
 <span data-ttu-id="7d8db-278">Чтобы возобновить экземпляр рабочего процесса, ведущее приложение должно предоставить определение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-278">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="7d8db-279">В этом учебнике описано 3 типа рабочих процессов и далее предоставлено несколько версий этих типов.</span><span class="sxs-lookup"><span data-stu-id="7d8db-279">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="7d8db-280">`WorkflowIdentity` позволяет ведущему приложению связать идентификационные данные с сохраненным экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-280">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="7d8db-281">В этом разделе показано, как создать служебный класс, который поможет сопоставить идентификационные данные из сохраненного экземпляра рабочего процесса с соответствующим определением рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-281">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="7d8db-282">Дополнительные сведения о `WorkflowIdentity` и управления версиями, см. в разделе [с помощью WorkflowIdentity и управления версиями](using-workflowidentity-and-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="7d8db-282">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>  
  
1. <span data-ttu-id="7d8db-283">Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **добавить**, **класс**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-283">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="7d8db-284">Тип `WorkflowVersionMap` в **имя** поле и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-284">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>  
  
2. <span data-ttu-id="7d8db-285">Добавьте следующие инструкции `using` или `Imports` в начало файла с другими инструкциями `using` или `Imports`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-285">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>  
  
    ```vb  
    Imports NumberGuessWorkflowActivities  
    Imports System.Activities  
    ```  
  
    ```csharp  
    using NumberGuessWorkflowActivities;  
    using System.Activities;  
    ```  
  
3. <span data-ttu-id="7d8db-286">Замените объявление класса `WorkflowVersionMap` следующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="7d8db-286">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {          
            return identity.ToString();  
       }  
    }  
    ```  
  
     <span data-ttu-id="7d8db-287">`WorkflowVersionMap` содержит три удостоверения рабочего процесса, которые сопоставляются с тремя определениями рабочих процессов из этого учебника и используются в следующих разделах при запуске и возобновлении рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="7d8db-287">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>  
  
### <a name="BKMK_StartWorkflow"></a> <span data-ttu-id="7d8db-288">Чтобы запустить новый рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="7d8db-288">To start a new workflow</span></span>  
  
1. <span data-ttu-id="7d8db-289">Добавьте обработчик событий `Click` для `NewGame`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-289">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="7d8db-290">Чтобы добавить обработчик, перейдите в **конструкторе** для формы и дважды щелкните файл `NewGame`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-290">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="7d8db-291">Добавляется обработчик `NewGame_Click`, и активируется представление кода формы.</span><span class="sxs-lookup"><span data-stu-id="7d8db-291">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="7d8db-292">Когда пользователь нажимает эту кнопку, запускается новый рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="7d8db-292">Whenever the user clicks this button a new workflow is started.</span></span>  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="7d8db-293">Добавьте следующий код в обработчик события щелчка.</span><span class="sxs-lookup"><span data-stu-id="7d8db-293">Add the following code to the click handler.</span></span> <span data-ttu-id="7d8db-294">Этот код создает словарь входных аргументов для рабочего процесса, различаемых по имени аргумента.</span><span class="sxs-lookup"><span data-stu-id="7d8db-294">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="7d8db-295">Этот словарь содержит одну запись с диапазоном случайного созданных чисел, полученных из поля со списком диапазонов.</span><span class="sxs-lookup"><span data-stu-id="7d8db-295">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>  
  
    ```vb  
    Dim inputs As New Dictionary(Of String, Object)()  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
    ```  
  
    ```csharp  
    var inputs = new Dictionary<string, object>();  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
    ```  
  
3. <span data-ttu-id="7d8db-296">Затем добавьте следующий код, который запускает рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="7d8db-296">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="7d8db-297">`WorkflowIdentity` и определение рабочего процесса, соответствующие выбранному типу рабочего процесса, извлекаются с помощью вспомогательного класса `WorkflowVersionMap`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-297">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="7d8db-298">Затем создается новый экземпляр `WorkflowApplication` с помощью определения рабочего процесса, `WorkflowIdentity` и словаря входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="7d8db-298">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>  
  
    ```vb  
    Dim identity As WorkflowIdentity = Nothing  
    Select Case WorkflowType.SelectedItem.ToString()  
        Case "SequentialNumberGuessWorkflow"  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
        Case "StateMachineNumberGuessWorkflow"  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
        Case "FlowchartNumberGuessWorkflow"  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
    End Select  
  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
    Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
    ```  
  
    ```csharp  
    WorkflowIdentity identity = null;  
    switch (WorkflowType.SelectedItem.ToString())  
    {  
        case "SequentialNumberGuessWorkflow":  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;  
            break;  
  
        case "StateMachineNumberGuessWorkflow":  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;  
            break;  
  
        case "FlowchartNumberGuessWorkflow":  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;  
            break;  
    };  
  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
    ```  
  
4. <span data-ttu-id="7d8db-299">Затем необходимо добавить следующий код, который добавляет рабочий процесс в список рабочих процессов и отображает сведения о версии рабочего процесса на форме.</span><span class="sxs-lookup"><span data-stu-id="7d8db-299">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>  
  
    ```vb  
    'Add the workflow to the list and display the version information.  
    WorkflowStarting = True  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
    WorkflowVersion.Text = identity.ToString()  
    WorkflowStarting = False  
    ```  
  
    ```csharp  
    // Add the workflow to the list and display the version information.  
    WorkflowStarting = true;  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
    WorkflowVersion.Text = identity.ToString();  
    WorkflowStarting = false;  
    ```  
  
5. <span data-ttu-id="7d8db-300">Вызовите `ConfigureWorkflowApplication` для настройки хранилища экземпляров, расширений и обработчиков жизненного цикла рабочего процесса для экземпляра `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-300">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>  
  
    ```vb  
    'Configure the instance store, extensions, and   
    'workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
    ```  
  
    ```csharp  
    // Configure the instance store, extensions, and   
    // workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp);  
    ```  
  
6. <span data-ttu-id="7d8db-301">Теперь вызовите `Run`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-301">Finally, call `Run`.</span></span>  
  
    ```vb  
    'Start the workflow.  
    wfApp.Run()  
    ```  
  
    ```  
    // Start the workflow.  
    wfApp.Run();  
    ```  
  
     <span data-ttu-id="7d8db-302">Ниже приведен полный пример обработчика `NewGame_Click`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-302">The following example is the completed `NewGame_Click` handler.</span></span>  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
        'Start a new workflow.  
        Dim inputs As New Dictionary(Of String, Object)()  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
  
        Dim identity As WorkflowIdentity = Nothing  
        Select Case WorkflowType.SelectedItem.ToString()  
            Case "SequentialNumberGuessWorkflow"  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
            Case "StateMachineNumberGuessWorkflow"  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
            Case "FlowchartNumberGuessWorkflow"  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
        End Select  
  
        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
        Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
  
        'Add the workflow to the list and display the version information.  
        WorkflowStarting = True  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
        WorkflowVersion.Text = identity.ToString()  
        WorkflowStarting = False  
  
        'Configure the instance store, extensions, and   
        'workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Start the workflow.  
        wfApp.Run()  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
        var inputs = new Dictionary<string, object>();  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
  
        WorkflowIdentity identity = null;  
        switch (WorkflowType.SelectedItem.ToString())  
        {  
            case "SequentialNumberGuessWorkflow":  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;  
                break;  
  
            case "StateMachineNumberGuessWorkflow":  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;  
                break;  
  
            case "FlowchartNumberGuessWorkflow":  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;  
                break;  
        };  
  
        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
        WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
  
        // Add the workflow to the list and display the version information.  
        WorkflowStarting = true;  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
        WorkflowVersion.Text = identity.ToString();  
        WorkflowStarting = false;  
  
        // Configure the instance store, extensions, and   
        // workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Start the workflow.  
        wfApp.Run();  
    }  
    ```  
  
### <a name="BKMK_ResumeWorkflow"></a> <span data-ttu-id="7d8db-303">Возобновление рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-303">To resume a workflow</span></span>  
  
1. <span data-ttu-id="7d8db-304">Добавьте обработчик событий `Click` для `EnterGuess`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-304">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="7d8db-305">Чтобы добавить обработчик, перейдите в **конструкторе** для формы и дважды щелкните файл `EnterGuess`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-305">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="7d8db-306">Когда пользователь нажимает эту кнопку, возобновляется рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="7d8db-306">Whenever the user clicks this button a workflow is resumed.</span></span>  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="7d8db-307">Добавьте следующий код, чтобы убедиться в том, что рабочий процесс выбран в списке рабочих процессов и догадка пользователя верна.</span><span class="sxs-lookup"><span data-stu-id="7d8db-307">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim userGuess As Integer  
    If Not Int32.TryParse(Guess.Text, userGuess) Then  
        MessageBox.Show("Please enter an integer.")  
        Guess.SelectAll()  
        Guess.Focus()  
        Return  
    End If  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    int guess;  
    if (!Int32.TryParse(Guess.Text, out guess))  
    {  
        MessageBox.Show("Please enter an integer.");  
        Guess.SelectAll();  
        Guess.Focus();  
        return;  
    }  
    ```  
  
3. <span data-ttu-id="7d8db-308">Затем извлеките `WorkflowApplicationInstance` сохраненного экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-308">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="7d8db-309">`WorkflowApplicationInstance` представляет экземпляр сохраненного рабочего процесса, который еще не был связан с определением рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-309">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="7d8db-310">`DefinitionIdentity` экземпляра `WorkflowApplicationInstance` содержит `WorkflowIdentity` экземпляра сохраненного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-310">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="7d8db-311">В этом учебнике служебный класс `WorkflowVersionMap` используется для сопоставления `WorkflowIdentity` с соответствующим определением рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d8db-311">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="7d8db-312">Когда определение рабочего процесса получено, создается приложение `WorkflowApplication` на основе правильного определения.</span><span class="sxs-lookup"><span data-stu-id="7d8db-312">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>  
  
    ```vb  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = _  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
    ```  
  
    ```csharp  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf =  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
    ```  
  
4. <span data-ttu-id="7d8db-313">После создания `WorkflowApplication` настройте хранилище экземпляров, обработчики жизненного цикла рабочего процесса и расширения, вызвав `ConfigureWorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-313">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="7d8db-314">Эти шаги требуются каждый раз, когда создается новое приложение `WorkflowApplication`, и должны быть выполнены до того, как экземпляр рабочего процесса будет загружен в `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-314">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="7d8db-315">После загрузки рабочего процесса он возобновляется с догадкой пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d8db-315">After the workflow is loaded, it is resumed with the user's guess.</span></span>  
  
    ```vb  
    'Configure the extensions and lifecycle handlers.  
    'Do this before the instance is loaded. Once the instance is  
    'loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", userGuess)  
    ```  
  
    ```csharp  
    // Configure the extensions and lifecycle handlers.  
    // Do this before the instance is loaded. Once the instance is  
    // loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", guess);  
    ```  
  
5. <span data-ttu-id="7d8db-316">И наконец, очистите текстовое поле с догадкой и подготовьте форму для ввода другой догадки.</span><span class="sxs-lookup"><span data-stu-id="7d8db-316">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>  
  
    ```vb  
    'Clear the Guess textbox.  
    Guess.Clear()  
    Guess.Focus()  
    ```  
  
    ```csharp  
    // Clear the Guess textbox.  
    Guess.Clear();  
    Guess.Focus();  
    ```  
  
     <span data-ttu-id="7d8db-317">Ниже приведен полный пример обработчика `EnterGuess_Click`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-317">The following example is the completed `EnterGuess_Click` handler.</span></span>  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
        If WorkflowInstanceId = Guid.Empty Then  
            MessageBox.Show("Please select a workflow.")  
            Return  
        End If  
  
        Dim userGuess As Integer  
        If Not Int32.TryParse(Guess.Text, userGuess) Then  
            MessageBox.Show("Please enter an integer.")  
            Guess.SelectAll()  
            Guess.Focus()  
            Return  
        End If  
  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        'Use the persisted WorkflowIdentity to retrieve the correct workflow  
        'definition from the dictionary.  
        Dim wf As Activity = _  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
        'Associate the WorkflowApplication with the correct definition  
        Dim wfApp As WorkflowApplication = _  
            New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
        'Configure the extensions and lifecycle handlers.  
        'Do this before the instance is loaded. Once the instance is  
        'loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Load the workflow.  
        wfApp.Load(instance)  
  
        'Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", userGuess)  
  
        'Clear the Guess textbox.  
        Guess.Clear()  
        Guess.Focus()  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
        if (WorkflowInstanceId == Guid.Empty)  
        {  
            MessageBox.Show("Please select a workflow.");  
            return;  
        }  
  
        int guess;  
        if (!Int32.TryParse(Guess.Text, out guess))  
        {  
            MessageBox.Show("Please enter an integer.");  
            Guess.SelectAll();  
            Guess.Focus();  
            return;  
        }  
  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
        // Use the persisted WorkflowIdentity to retrieve the correct workflow  
        // definition from the dictionary.  
        Activity wf =  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
        // Associate the WorkflowApplication with the correct definition  
        WorkflowApplication wfApp =  
            new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
        // Configure the extensions and lifecycle handlers.  
        // Do this before the instance is loaded. Once the instance is  
        // loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Load the workflow.  
        wfApp.Load(instance);  
  
        // Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", guess);  
  
        // Clear the Guess textbox.  
        Guess.Clear();  
        Guess.Focus();  
    }  
    ```  
  
### <a name="BKMK_TerminateWorkflow"></a> <span data-ttu-id="7d8db-318">Завершение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d8db-318">To terminate a workflow</span></span>  
  
1. <span data-ttu-id="7d8db-319">Добавьте обработчик событий `Click` для `QuitGame`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-319">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="7d8db-320">Чтобы добавить обработчик, перейдите в **конструкторе** для формы и дважды щелкните файл `QuitGame`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-320">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="7d8db-321">Когда пользователь нажимает эту кнопку, рабочий процесс, выбранный на данный момент, завершается.</span><span class="sxs-lookup"><span data-stu-id="7d8db-321">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>  
  
    ```vb  
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void QuitGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="7d8db-322">Добавьте следующий код в обработчик `QuitGame_Click`:</span><span class="sxs-lookup"><span data-stu-id="7d8db-322">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="7d8db-323">Code First проверяет, что рабочий процесс выбран в списке рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="7d8db-323">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="7d8db-324">Затем он загружает сохраненный экземпляр в `WorkflowApplicationInstance`, использует `DefinitionIdentity` для получения правильного определения рабочего процесса и инициализирует `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-324">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="7d8db-325">После этого настраиваются расширения и обработчики жизненного цикла рабочего процесса с помощью метода `ConfigureWorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-325">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="7d8db-326">После настройки `WorkflowApplication` приложение загружается и вызывается метод `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="7d8db-326">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition.  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
    'Configure the extensions and lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Terminate the workflow.  
    wfApp.Terminate("User resigns.")  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
    // Configure the extensions and lifecycle handlers  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Terminate the workflow.  
    wfApp.Terminate("User resigns.");  
    ```  
  
### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="7d8db-327">Сборка и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="7d8db-327">To build and run the application</span></span>  
  
1. <span data-ttu-id="7d8db-328">Дважды щелкните **Program.cs** (или **Module1.vb**) в **обозревателе решений** для отображения кода.</span><span class="sxs-lookup"><span data-stu-id="7d8db-328">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>  
  
2. <span data-ttu-id="7d8db-329">Добавьте следующие инструкции `using` (или `Imports`) в начало файла с другими инструкциями `using` (или `Imports`).</span><span class="sxs-lookup"><span data-stu-id="7d8db-329">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
3. <span data-ttu-id="7d8db-330">Удалите или закомментируйте существующий рабочий процесс, код из размещения [как: Запуск рабочего процесса](how-to-run-a-workflow.md)и замените его следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="7d8db-330">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>  
  
    ```vb  
    Sub Main()  
        Application.EnableVisualStyles()  
        Application.Run(New WorkflowHostForm())  
    End Sub  
    ```  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        Application.EnableVisualStyles();  
        Application.Run(new WorkflowHostForm());  
    }  
    ```  
  
4. <span data-ttu-id="7d8db-331">Щелкните правой кнопкой мыши **NumberGuessWorkflowHost** в **обозревателе решений** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-331">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="7d8db-332">В **приложения** задайте **приложения Windows** для **тип выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-332">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="7d8db-333">Этот шаг не обязателен, но, если его не выполнить, вместе с формой отображается окно консоли.</span><span class="sxs-lookup"><span data-stu-id="7d8db-333">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>  
  
5. <span data-ttu-id="7d8db-334">Нажмите клавиши Ctrl+Shift+B, чтобы создать приложение.</span><span class="sxs-lookup"><span data-stu-id="7d8db-334">Press Ctrl+Shift+B to build the application.</span></span>  
  
6. <span data-ttu-id="7d8db-335">Убедитесь, что **NumberGuessWorkflowHost** присвоено значение в качестве запускаемого приложения, и нажмите Ctrl + F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="7d8db-335">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>  
  
7. <span data-ttu-id="7d8db-336">Выберите диапазон для игры на угадывание и тип рабочего процесса для запуска и нажмите кнопку **новая игра**.</span><span class="sxs-lookup"><span data-stu-id="7d8db-336">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="7d8db-337">Введите догадку в **предположение** поле и нажмите кнопку **Go** Чтобы отправить догадку.</span><span class="sxs-lookup"><span data-stu-id="7d8db-337">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="7d8db-338">Обратите внимание, что выходные данные действий `WriteLine` отображаются на форме.</span><span class="sxs-lookup"><span data-stu-id="7d8db-338">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>  
  
8. <span data-ttu-id="7d8db-339">Запустите несколько рабочих процессов, с помощью разных типов рабочих процессов и диапазонов чисел, введите некоторые догадки и переключение между рабочими процессами, выбрав из **идентификатор экземпляра рабочего процесса** списка.</span><span class="sxs-lookup"><span data-stu-id="7d8db-339">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>  
  
     <span data-ttu-id="7d8db-340">Обратите внимание, что, если перейти к новому рабочему процессу, предыдущие догадки и ход выполнения рабочего процесса не отображаются в окне состояния.</span><span class="sxs-lookup"><span data-stu-id="7d8db-340">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="7d8db-341">Состояние недоступно, так как оно не перехвачено и не сохранено.</span><span class="sxs-lookup"><span data-stu-id="7d8db-341">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="7d8db-342">На следующем шаге этого руководства [как: Создать настраиваемый участник отслеживания](how-to-create-a-custom-tracking-participant.md), создание настраиваемого участника отслеживания, сохраняет эти данные.</span><span class="sxs-lookup"><span data-stu-id="7d8db-342">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
