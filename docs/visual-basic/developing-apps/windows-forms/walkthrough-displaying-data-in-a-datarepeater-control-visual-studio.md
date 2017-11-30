---
title: "Пошаговое руководство. Отображение данных в элементе управления DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39c3b56404c981e674766354463e23aa349994cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="d7187-102">Пошаговое руководство. Отображение данных в элементе управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d7187-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="d7187-103">Это пошаговое руководство содержит базовый сценарий для отображения связанных данных в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> от начала и до конца.</span><span class="sxs-lookup"><span data-stu-id="d7187-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="d7187-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d7187-104">Prerequisite</span></span>  
 <span data-ttu-id="d7187-105">В данном пошаговом руководстве требуется доступ к учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d7187-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="d7187-106">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла [Центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088).</span><span class="sxs-lookup"><span data-stu-id="d7187-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="d7187-107">Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="d7187-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d7187-108">Обзор</span><span class="sxs-lookup"><span data-stu-id="d7187-108">Overview</span></span>  
 <span data-ttu-id="d7187-109">Данное пошаговое руководство состоит из четырех основных задач.</span><span class="sxs-lookup"><span data-stu-id="d7187-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="d7187-110">Создание решения.</span><span class="sxs-lookup"><span data-stu-id="d7187-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="d7187-111">Добавление элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="d7187-112">Добавление источника данных.</span><span class="sxs-lookup"><span data-stu-id="d7187-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="d7187-113">Добавление элементов управления с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="d7187-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="d7187-114">Создание решения DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="d7187-115">На первом шаге создаются проект и решение.</span><span class="sxs-lookup"><span data-stu-id="d7187-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="d7187-116">Создание решения DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="d7187-117">В меню **Файл** Visual Studio выберите команду **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="d7187-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="d7187-118">В области **Типы проектов** диалогового окна **Создать проект** разверните узел **Visual Basic**, а затем щелкните **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d7187-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="d7187-119">Выберите **Приложение Windows Forms** в области **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="d7187-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="d7187-120">В поле **Имя файла** введите `DataRepeaterApp`.</span><span class="sxs-lookup"><span data-stu-id="d7187-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="d7187-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d7187-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="d7187-122">Откроется конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d7187-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="d7187-123">Выберите форму в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d7187-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="d7187-124">В окне **Свойства** присвойте свойству **Размер** значение `800, 700`.</span><span class="sxs-lookup"><span data-stu-id="d7187-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="d7187-125">Добавление элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="d7187-126">На этом шаге в форму добавляется элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="d7187-127">Добавление элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="d7187-128">В меню **Вид** выберите пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="d7187-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="d7187-129">Откроется **Панель элементов** .</span><span class="sxs-lookup"><span data-stu-id="d7187-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="d7187-130">Перейдите на вкладку **Visual Basic PowerPacks** .</span><span class="sxs-lookup"><span data-stu-id="d7187-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="d7187-131">Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> в форму **Form1**.</span><span class="sxs-lookup"><span data-stu-id="d7187-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="d7187-132">В окне "Свойства" присвойте свойству **Расположение** значение `0, 25`.</span><span class="sxs-lookup"><span data-stu-id="d7187-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="d7187-133">Установите значение свойства **Размер** равным `460, 600`.</span><span class="sxs-lookup"><span data-stu-id="d7187-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="d7187-134">Добавление источника данных</span><span class="sxs-lookup"><span data-stu-id="d7187-134">Adding a Data Source</span></span>  
 <span data-ttu-id="d7187-135">На этом шаге добавляется источник данных для элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="d7187-136">Добавление источника данных</span><span class="sxs-lookup"><span data-stu-id="d7187-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="d7187-137">В меню **Данные** выберите команду **Показать источники данных**.</span><span class="sxs-lookup"><span data-stu-id="d7187-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="d7187-138">В окне **Источники данных** выберите **Добавить новый источник данных**.</span><span class="sxs-lookup"><span data-stu-id="d7187-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="d7187-139">На странице **Выбор типа источника данных** выберите элемент **База данных** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d7187-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d7187-140">На странице **Выбор подключения к базе данных** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d7187-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="d7187-141">Если подключение к учебной базе данных "Борей" доступно в раскрывающемся списке, то выберите его.</span><span class="sxs-lookup"><span data-stu-id="d7187-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="d7187-142">-или-</span><span class="sxs-lookup"><span data-stu-id="d7187-142">-or-</span></span>  
  
    -   <span data-ttu-id="d7187-143">Нажмите кнопку **Создать подключение** для создания подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="d7187-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="d7187-144">Дополнительные сведения см. в разделе [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span><span class="sxs-lookup"><span data-stu-id="d7187-144">For more information, see [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span></span>  
  
5.  <span data-ttu-id="d7187-145">Если базе данных требуется пароль, выберите параметр для включения конфиденциальных данных и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d7187-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7187-146">Если появится диалоговое окно, нажмите кнопку **Да** , чтобы сохранить файл в проекте.</span><span class="sxs-lookup"><span data-stu-id="d7187-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="d7187-147">На странице **Сохранение подключения в файле конфигурации приложения** нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="d7187-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="d7187-148">Разверните узел **Таблицы** на странице **Выбор объектов базы данных** .</span><span class="sxs-lookup"><span data-stu-id="d7187-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="d7187-149">Установите флажки для таблиц **Клиенты** и **Заказы** , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d7187-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="d7187-150">**NorthwindDataSet** добавляется в проект, и таблицы **Клиенты** и **Заказы** отображаются в окне **Источники данных** .</span><span class="sxs-lookup"><span data-stu-id="d7187-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="d7187-151">Добавление элементов управления с привязкой к данным</span><span class="sxs-lookup"><span data-stu-id="d7187-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="d7187-152">На этом шаге элементы управления с привязкой к данным добавляются в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="d7187-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="d7187-153">Чтобы добавить элементы управления с привязкой к данным</span><span class="sxs-lookup"><span data-stu-id="d7187-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="d7187-154">В окне **Источники данных** выберите узел верхнего уровня для таблицы **Клиенты** .</span><span class="sxs-lookup"><span data-stu-id="d7187-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="d7187-155">Измените тип удаления таблицы на **Сведения** , выбрав **Сведения** в раскрывающемся списке в узле таблицы.</span><span class="sxs-lookup"><span data-stu-id="d7187-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="d7187-156">Выберите узел таблицы **Клиенты** и перетащите его в область шаблона (верхняя часть) элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d7187-157">Элемент управления <xref:System.Windows.Forms.BindingNavigator> добавляется в форму, а компоненты **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**и **CustomersBindingNavigator** добавляются в область компонентов.</span><span class="sxs-lookup"><span data-stu-id="d7187-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="d7187-158">Выберите все поля и их связанные подписи и разместите их у левого края области шаблона элемента.</span><span class="sxs-lookup"><span data-stu-id="d7187-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="d7187-159">Выберите последние пять полей (**Область**, **Почтовый индекс**, **Страна**, **Телефон**и **Факс**) и их связанные подписи и поместите их вверху справа от первых шести полей.</span><span class="sxs-lookup"><span data-stu-id="d7187-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="d7187-160">Выберите шаблон элемента (верхняя область элемента управления).</span><span class="sxs-lookup"><span data-stu-id="d7187-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="d7187-161">В окне "Свойства" присвойте свойству **Размер** значение `427, 170`.</span><span class="sxs-lookup"><span data-stu-id="d7187-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="d7187-162">Теперь у вас есть рабочее приложение, которое будет отображать повторяющийся список клиентов.</span><span class="sxs-lookup"><span data-stu-id="d7187-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="d7187-163">Можно нажать клавишу F5, чтобы запустить приложение, изменить данные и добавить или удалить записи клиентов.</span><span class="sxs-lookup"><span data-stu-id="d7187-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="d7187-164">На следующих необязательных этапах вы узнаете, как настроить элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="d7187-165">Дальнейшие действия (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d7187-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="d7187-166">Эта часть пошагового руководства состоит из четырех дополнительных задач.</span><span class="sxs-lookup"><span data-stu-id="d7187-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="d7187-167">Изменение внешнего вида элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="d7187-168">Запрет добавления или удаления записей пользователями.</span><span class="sxs-lookup"><span data-stu-id="d7187-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="d7187-169">Добавление функции поиска в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="d7187-170">Добавление основной таблицы и таблицы сведений в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="d7187-171">Изменение внешнего вида элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="d7187-172">На этом необязательном шаге выполняется изменение `BackColor` элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> во время разработки.</span><span class="sxs-lookup"><span data-stu-id="d7187-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="d7187-173">Можно также добавить код для отображения столбцов с чередованием цвета и условного изменения `ForeColor` подписи.</span><span class="sxs-lookup"><span data-stu-id="d7187-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="d7187-174">Изменение внешнего вида элемента управления</span><span class="sxs-lookup"><span data-stu-id="d7187-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="d7187-175">В конструкторе Windows Forms выберите основную (нижнюю) область элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="d7187-176">В окне "Свойства" задайте свойству `BackColor` значение "Белый".</span><span class="sxs-lookup"><span data-stu-id="d7187-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="d7187-177">Дважды щелкните <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="d7187-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="d7187-178">В редакторе кода в раскрывающемся списке выберите **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="d7187-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="d7187-179">В обработчике событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> добавьте следующий код для изменения `BackColor`:</span><span class="sxs-lookup"><span data-stu-id="d7187-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="d7187-180">В обработчике событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> добавьте следующий код для изменения `ForeColor` подписи в зависимости от условия:</span><span class="sxs-lookup"><span data-stu-id="d7187-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="d7187-181">Нажмите клавишу F5, чтобы запустить приложение и просмотреть настройки.</span><span class="sxs-lookup"><span data-stu-id="d7187-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="d7187-182">Запрет добавления или удаления записей пользователями</span><span class="sxs-lookup"><span data-stu-id="d7187-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="d7187-183">На этом необязательном шаге добавляется код, который запрещает пользователям добавлять или удалять записи в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="d7187-184">Запрет добавления или удаления записей пользователями</span><span class="sxs-lookup"><span data-stu-id="d7187-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="d7187-185">В конструкторе Windows Forms дважды щелкните форму, чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="d7187-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="d7187-186">Добавьте следующий код в событие `Form_Load` :</span><span class="sxs-lookup"><span data-stu-id="d7187-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="d7187-187">В раскрывающемся списке "Имя класса" выберите **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="d7187-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="d7187-188">В раскрывающемся списке "Имя метода" выберите **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="d7187-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="d7187-189">Добавьте следующий код в обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` .</span><span class="sxs-lookup"><span data-stu-id="d7187-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d7187-190">Этот шаг необходим, так как <xref:System.Windows.Forms.BindingSource> будет активировать кнопку **DeleteItem** при каждом изменении текущей записи.</span><span class="sxs-lookup"><span data-stu-id="d7187-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="d7187-191">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="d7187-191">Press F5 to run the application.</span></span> <span data-ttu-id="d7187-192">Обратите внимание, что кнопка **DeleteItem** отключена и вы не можете удалять элементы с помощью клавиши DELETE.</span><span class="sxs-lookup"><span data-stu-id="d7187-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="d7187-193">Добавление функции поиска в элемент управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="d7187-194">На этом необязательном шаге реализуется возможность поиска значения в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d7187-195">При нахождении искомой строки элемент управления выбирает элемент, содержащий значение, и прокручивает элемент в представлении.</span><span class="sxs-lookup"><span data-stu-id="d7187-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="d7187-196">Добавление функции поиска</span><span class="sxs-lookup"><span data-stu-id="d7187-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="d7187-197">Перетащите элемент управления <xref:System.Windows.Forms.TextBox> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d7187-198">Расположите его под элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="d7187-199">В окне "Свойства" измените значение свойства **Имя** на **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="d7187-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="d7187-200">Перетащите элемент управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d7187-201">Расположите его под элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="d7187-202">В окне "Свойства" измените значение свойства **Имя** на **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="d7187-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="d7187-203">Задайте для свойства **Текст** значение **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="d7187-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="d7187-204">Дважды щелкните элемент управления <xref:System.Windows.Forms.Button> , чтобы открыть редактор кода, и добавьте следующий код в обработчик событий `SearchButton_Click` :</span><span class="sxs-lookup"><span data-stu-id="d7187-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="d7187-205">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="d7187-205">Press F5 to run the application.</span></span> <span data-ttu-id="d7187-206">Введите код клиента в **SearchTextBox** и нажмите кнопку **Поиск** .</span><span class="sxs-lookup"><span data-stu-id="d7187-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="d7187-207">Добавление основной таблицы и таблицы сведений в элемент управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="d7187-208">На этом необязательном шаге добавляется второй элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> для отображения связанных заказов для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="d7187-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="d7187-209">Добавление основной таблицы и таблицы сведений</span><span class="sxs-lookup"><span data-stu-id="d7187-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="d7187-210">Перетащите второй элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму.</span><span class="sxs-lookup"><span data-stu-id="d7187-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="d7187-211">В окне "Свойства" присвойте свойству **Расположение** значение `465, 25`.</span><span class="sxs-lookup"><span data-stu-id="d7187-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="d7187-212">Установите значение свойства **Размер** равным `315, 600`.</span><span class="sxs-lookup"><span data-stu-id="d7187-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="d7187-213">В окне **Источники данных** разверните узел таблицы **Клиенты** и выберите узел сведений для таблицы **Заказы** .</span><span class="sxs-lookup"><span data-stu-id="d7187-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="d7187-214">Измените тип удаления таблицы **Заказы** на "Сведения", выбрав **Сведения** в раскрывающемся списке в узле таблицы.</span><span class="sxs-lookup"><span data-stu-id="d7187-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="d7187-215">Перетащите этот узел таблицы **Заказы** в область шаблона (верхняя часть) второго элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d7187-216">Компоненты **OrdersBindingSource** и **OrdersTableAdapter** добавляются в область компонентов.</span><span class="sxs-lookup"><span data-stu-id="d7187-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="d7187-217">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="d7187-217">Press F5 to run the application.</span></span> <span data-ttu-id="d7187-218">При выборе каждого клиента в первом элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> заказы для этого клиента отображаются во втором элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="d7187-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7187-219">См. также</span><span class="sxs-lookup"><span data-stu-id="d7187-219">See Also</span></span>  
 [<span data-ttu-id="d7187-220">Общие сведения об элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-221">Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-222">Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-223">Практическое руководство. Изменение структуры элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-224">Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-225">Практическое руководство. Поиск данных в элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-226">Как: создать Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d7187-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="d7187-227">Практическое руководство. Изменение внешнего вида элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d7187-228">Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [<span data-ttu-id="d7187-229">Устранение неполадок при использовании элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="d7187-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
