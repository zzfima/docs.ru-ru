---
title: Практическое руководство. Связывание элементов управления Windows Forms с компонентом BindingSource с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 95f375d8845c60441aa5eefdd37e32541ea2d5a7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042313"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="b0be8-102">Практическое руководство. Связывание элементов управления Windows Forms с компонентом BindingSource с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="b0be8-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="b0be8-103">После добавления элементов управления в форму и определения пользовательского интерфейса для вашего приложения, можно привязать элементы управления к источнику данных, чтобы во время выполнения, пользователи могут изменять и сохранять данные, связанные с приложением.</span><span class="sxs-lookup"><span data-stu-id="b0be8-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="b0be8-104">Привязка одного или нескольких элементов управления в Windows Forms проще всего с помощью <xref:System.Windows.Forms.BindingSource> управления в качестве моста между элементов управления в форме и источником данных.</span><span class="sxs-lookup"><span data-stu-id="b0be8-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="b0be8-105">Один или несколько элементов управления в форме можно привязать к данным; в следующей процедуре <xref:System.Windows.Forms.TextBox> привязке элемента управления к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="b0be8-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="b0be8-106">Чтобы завершить процедуру, предполагается, что будет привязан к источнику данных, производный от базы данных.</span><span class="sxs-lookup"><span data-stu-id="b0be8-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="b0be8-107">Дополнительные сведения о создании источников данных из хранилищ данных, см. в разделе [добавляются новые источники данных](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="b0be8-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0be8-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="b0be8-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b0be8-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="b0be8-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b0be8-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b0be8-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="b0be8-111">Для привязки элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="b0be8-111">To bind a control at design time</span></span>  
  
1.  <span data-ttu-id="b0be8-112">Перетащите <xref:System.Windows.Forms.TextBox> элемента управления в форму.</span><span class="sxs-lookup"><span data-stu-id="b0be8-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2.  <span data-ttu-id="b0be8-113">В **свойства** окна:</span><span class="sxs-lookup"><span data-stu-id="b0be8-113">In the **Properties** window:</span></span>  
  
    1.  <span data-ttu-id="b0be8-114">Разверните **(DataBindings)** узла.</span><span class="sxs-lookup"><span data-stu-id="b0be8-114">Expand the **(DataBindings)** node.</span></span>  
  
    2.  <span data-ttu-id="b0be8-115">Щелкните стрелку рядом с полем <xref:System.Windows.Forms.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b0be8-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="b0be8-116">**DataSource** открывает редактор типов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b0be8-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="b0be8-117">Если источник данных ранее был настроен для проекта или формы, он будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="b0be8-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3.  <span data-ttu-id="b0be8-118">Щелкните элемент **Добавить источник данных проекта**, чтобы подключиться к данным и создать источник данных.</span><span class="sxs-lookup"><span data-stu-id="b0be8-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4.  <span data-ttu-id="b0be8-119">На странице приветствия **Мастер настройки источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b0be8-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="b0be8-120">На **Выбор типа источника данных** выберите **базы данных**.</span><span class="sxs-lookup"><span data-stu-id="b0be8-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6.  <span data-ttu-id="b0be8-121">На **Выбор подключения к данным** выберите подключение к данным из списка доступных подключений.</span><span class="sxs-lookup"><span data-stu-id="b0be8-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="b0be8-122">Если необходимое подключение данных не доступны выберите **новое подключение** для создания нового подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="b0be8-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7.  <span data-ttu-id="b0be8-123">Выберите **Да, сохранить подключение** сохранить строку подключения в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b0be8-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8.  <span data-ttu-id="b0be8-124">Выберите объекты базы данных, чтобы перенести их в приложение.</span><span class="sxs-lookup"><span data-stu-id="b0be8-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="b0be8-125">В этом случае выберите поле в таблице, в котором вы хотите <xref:System.Windows.Forms.TextBox> для отображения.</span><span class="sxs-lookup"><span data-stu-id="b0be8-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="b0be8-126">Если необходимо, замените имя набора данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b0be8-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="b0be8-127">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b0be8-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="b0be8-128">В **свойства** окно, щелкните стрелку рядом с полем <xref:System.Windows.Forms.TextBox.Text%2A> свойство еще раз.</span><span class="sxs-lookup"><span data-stu-id="b0be8-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="b0be8-129">В **DataSource** редактора типов пользовательского интерфейса, выберите имя поля для привязки <xref:System.Windows.Forms.TextBox> для.</span><span class="sxs-lookup"><span data-stu-id="b0be8-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="b0be8-130">**DataSource** типа пользовательского интерфейса редактора закроется, а набор данных, <xref:System.Windows.Forms.BindingSource> и адаптер таблицы для что подключение к данным добавляются в форму.</span><span class="sxs-lookup"><span data-stu-id="b0be8-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0be8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b0be8-131">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [<span data-ttu-id="b0be8-132">Добавление новых источников данных</span><span class="sxs-lookup"><span data-stu-id="b0be8-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)  
 [<span data-ttu-id="b0be8-133">Окно "Источники данных"</span><span class="sxs-lookup"><span data-stu-id="b0be8-133">Data Sources Window</span></span>](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
