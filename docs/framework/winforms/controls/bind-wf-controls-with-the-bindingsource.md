---
title: Практическое руководство. Связывание элементов управления Windows Forms с компонентом BindingSource с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 180fafa9ace5927fd84ec5dc0a1b2a342f771efd
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040018"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="d9e2a-102">Практическое руководство. Связывание элементов управления Windows Forms с компонентом BindingSource с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d9e2a-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="d9e2a-103">После добавления элементов управления в форму и определения пользовательского интерфейса для приложения можно привязать элементы управления к источнику данных, чтобы во время выполнения пользователи могли изменять и сохранять данные, связанные с приложением.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="d9e2a-104">Привязка элемента управления или ряда элементов управления в Windows Forms наиболее легко осуществляется с помощью <xref:System.Windows.Forms.BindingSource> элемента управления в качестве моста между элементами управления в форме и источником данных.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="d9e2a-105">Один или несколько элементов управления формы могут быть привязаны к данным; в следующей процедуре <xref:System.Windows.Forms.TextBox> элемент управления привязан к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="d9e2a-106">Для выполнения этой процедуры предполагается, что будет выполнена привязка к источнику данных, производному от базы данных.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="d9e2a-107">Дополнительные сведения о создании источников данных из других хранилищ данных см. в разделе [Добавление новых источников данных](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d9e2a-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="d9e2a-108">Привязка элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="d9e2a-108">To bind a control at design time</span></span>

1. <span data-ttu-id="d9e2a-109"><xref:System.Windows.Forms.TextBox> Перетащите элемент управления в форму.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="d9e2a-110">В окне " **Свойства** ":</span><span class="sxs-lookup"><span data-stu-id="d9e2a-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="d9e2a-111">Разверните узел **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="d9e2a-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="d9e2a-112">Щелкните стрелку рядом <xref:System.Windows.Forms.TextBox.Text%2A> со свойством.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="d9e2a-113">Откроется редактор типов пользовательского интерфейса **DataSource** .</span><span class="sxs-lookup"><span data-stu-id="d9e2a-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="d9e2a-114">Если источник данных ранее был настроен для проекта или формы, он появится.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="d9e2a-115">Щелкните элемент **Добавить источник данных проекта**, чтобы подключиться к данным и создать источник данных.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="d9e2a-116">На странице приветствия **Мастер настройки источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="d9e2a-117">На странице **Выбор типа источника данных** выберите **база данных**.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="d9e2a-118">На странице **Выбор подключения к данным** выберите подключение к данным из списка доступных подключений.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="d9e2a-119">Если нужное подключение к данным недоступно, выберите **создать подключение** , чтобы создать новое подключение к данным.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="d9e2a-120">Выберите **Да, сохранить подключение** , чтобы сохранить строку подключения в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="d9e2a-121">Выберите объекты базы данных, чтобы перенести их в приложение.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="d9e2a-122">В этом случае выберите поле в таблице, которое <xref:System.Windows.Forms.TextBox> нужно отобразить.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="d9e2a-123">Если необходимо, замените имя набора данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="d9e2a-124">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-124">Click **Finish**.</span></span>

11. <span data-ttu-id="d9e2a-125">В окне **Свойства** снова щелкните стрелку рядом <xref:System.Windows.Forms.TextBox.Text%2A> со свойством.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="d9e2a-126">В окне Редактор типов пользовательского интерфейса **DataSource** выберите имя поля для привязки <xref:System.Windows.Forms.TextBox> к.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="d9e2a-127">Редактор типов пользовательского интерфейса **DataSource** закрывается, а набор <xref:System.Windows.Forms.BindingSource> данных и адаптер таблицы, относящиеся к этому соединению с данными, добавляются в форму.</span><span class="sxs-lookup"><span data-stu-id="d9e2a-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9e2a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d9e2a-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="d9e2a-129">Добавление новых источников данных</span><span class="sxs-lookup"><span data-stu-id="d9e2a-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="d9e2a-130">[Окно "источники данных"](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d9e2a-130">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
