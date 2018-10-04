---
title: Пошаговое руководство. Кэширование данных приложения WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 1eddf3ad52bab6ef4665d7c3691353fa9c54574c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793686"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="cb0f9-102">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="cb0f9-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="cb0f9-103">Кэширование позволяет хранить данные в памяти для быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="cb0f9-104">Еще раз доступ к данным приложения могут получать данные из кэша вместо их извлечения из исходного источника.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="cb0f9-105">Это может повысить производительность и масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-105">This can improve performance and scalability.</span></span> <span data-ttu-id="cb0f9-106">Кроме того, кэширование обеспечивает доступность данных при временной недоступности источника данных.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="cb0f9-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Предоставляет классы, которые позволяют использовать кэширование в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="cb0f9-108">Эти классы находятся в папке <xref:System.Runtime.Caching> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="cb0f9-109"><xref:System.Runtime.Caching> Пространство имен впервые появилось в [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb0f9-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cb0f9-110">Это пространство имен обеспечивает кэширование доступен для всех [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="cb0f9-111">В предыдущих версиях [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] кэширование было доступно только в пространстве имен <xref:System.Web> и поэтому требовало зависимости от классов ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="cb0f9-112">В этом пошаговом руководстве показано, как использовать функции кэширования, которая доступна в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] как часть [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb0f9-113">В этом пошаговом руководстве кэшировать содержимое текстового файла.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="cb0f9-114">В данном пошаговом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-114">Tasks illustrated in this walkthrough include the following:</span></span>

-   <span data-ttu-id="cb0f9-115">Создание проекта приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-115">Creating a WPF application project.</span></span>

-   <span data-ttu-id="cb0f9-116">Добавление ссылки на [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb0f9-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

-   <span data-ttu-id="cb0f9-117">Инициализация кэша.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-117">Initializing a cache.</span></span>

-   <span data-ttu-id="cb0f9-118">Добавление записи кэша, который содержит содержимое текстового файла.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-118">Adding a cache entry that contains the contents of a text file.</span></span>

-   <span data-ttu-id="cb0f9-119">Предоставление используется политика вытеснения для записи кэша.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-119">Providing an eviction policy for the cache entry.</span></span>

-   <span data-ttu-id="cb0f9-120">Отслеживание пути кэшированный файл и уведомление о экземпляра кэша изменения отслеживаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb0f9-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cb0f9-121">Prerequisites</span></span>
 <span data-ttu-id="cb0f9-122">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-122">In order to complete this walkthrough, you will need:</span></span>

-   <span data-ttu-id="cb0f9-123">Microsoft Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-123">Microsoft Visual Studio 2010.</span></span>

-   <span data-ttu-id="cb0f9-124">Текстовый файл, который содержит небольшой объем текста.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="cb0f9-125">(Содержимое файла текст будет отображаться в окне сообщения.) Код, показанный в этом пошаговом руководстве предполагается, что вы работаете в следующем файле:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="cb0f9-126">Тем не менее можно использовать любой текстовый файл и внести небольшие изменения в код в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="cb0f9-127">Создание проекта приложения WPF</span><span class="sxs-lookup"><span data-stu-id="cb0f9-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="cb0f9-128">Начнем с создания проекта приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="cb0f9-129">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="cb0f9-129">To create a WPF application</span></span>

1.  <span data-ttu-id="cb0f9-130">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-130">Start Visual Studio.</span></span>

2.  <span data-ttu-id="cb0f9-131">В **файл** меню, щелкните **New**, а затем нажмите кнопку **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="cb0f9-132">Откроется диалоговое окно **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-132">The **New Project** dialog box is displayed.</span></span>

3.  <span data-ttu-id="cb0f9-133">В разделе **установленные шаблоны**, выберите язык программирования, который вы хотите использовать (**Visual Basic** или **Visual C#**).</span><span class="sxs-lookup"><span data-stu-id="cb0f9-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4.  <span data-ttu-id="cb0f9-134">В **новый проект** выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="cb0f9-135">Если вы не видите **приложение WPF** шаблона, убедитесь, что вы используете версию [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поддерживает WPF.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="cb0f9-136">В **новый проект** выберите [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] из списка.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5.  <span data-ttu-id="cb0f9-137">В **имя** текстовое поле, введите имя для проекта.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="cb0f9-138">Например, можно ввести **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-138">For example, you can enter **WPFCaching**.</span></span>

6.  <span data-ttu-id="cb0f9-139">Выберите **создать каталог для решения** "флажок".</span><span class="sxs-lookup"><span data-stu-id="cb0f9-139">Select the **Create directory for solution** check box.</span></span>

7.  <span data-ttu-id="cb0f9-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-140">Click **OK**.</span></span>

     <span data-ttu-id="cb0f9-141">Откроется конструктор WPF в **разработки** просмотра и отображает файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="cb0f9-142">Visual Studio создает **Мой проект** папка, файл Application.xaml и файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="cb0f9-143">Нацеливание на платформу .NET Framework и Добавление ссылки на сборки кэширования</span><span class="sxs-lookup"><span data-stu-id="cb0f9-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="cb0f9-144">По умолчанию приложения WPF предназначены [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb0f9-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="cb0f9-145">Чтобы использовать <xref:System.Runtime.Caching> пространства имен в приложении WPF, приложение должно использовать платформу [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (не [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) и необходимо включить ссылку на пространство имен.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="cb0f9-146">Таким образом, следующим шагом является изменение целевой платформы .NET Framework и добавьте ссылку на <xref:System.Runtime.Caching> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="cb0f9-147">Процедура изменения целевой платформы .NET Framework отличается в проекте Visual Basic и в проекте Visual C#.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="cb0f9-148">Изменение целевой платформы .NET Framework в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb0f9-148">To change the target .NET Framework in Visual Basic</span></span>

1.  <span data-ttu-id="cb0f9-149">В **обозревателя решений**, щелкните правой кнопкой мыши имя проекта и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="cb0f9-150">Откроется окно свойств для приложения.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-150">The properties window for the application is displayed.</span></span>

2.  <span data-ttu-id="cb0f9-151">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-151">Click the **Compile** tab.</span></span>

3.  <span data-ttu-id="cb0f9-152">В нижней части окна, щелкните **Дополнительные параметры компиляции...** .</span><span class="sxs-lookup"><span data-stu-id="cb0f9-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="cb0f9-153">**Дополнительные параметры компилятора** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4.  <span data-ttu-id="cb0f9-154">В **целевой платформы (все конфигурации)** выберите [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb0f9-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cb0f9-155">(Не выбирайте [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="cb0f9-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5.  <span data-ttu-id="cb0f9-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-156">Click **OK**.</span></span>

     <span data-ttu-id="cb0f9-157">Откроется диалоговое окно **Изменение целевой рабочей среды**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-157">The **Target Framework Change** dialog box is displayed.</span></span>

6.  <span data-ttu-id="cb0f9-158">В **Изменение целевой платформы** диалоговом окне щелкните **Да**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="cb0f9-159">Проект будет закрыт и вновь открыт.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-159">The project is closed and is then reopened.</span></span>

7.  <span data-ttu-id="cb0f9-160">Добавьте ссылку на сборку кэширования, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-160">Add a reference to the caching assembly by following these steps:</span></span>

    1.  <span data-ttu-id="cb0f9-161">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2.  <span data-ttu-id="cb0f9-162">Выберите **.NET** выберите `System.Runtime.Caching`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="cb0f9-163">Изменение целевой платформы .NET Framework в проекте Visual C#</span><span class="sxs-lookup"><span data-stu-id="cb0f9-163">To change the target .NET Framework in a Visual C# project</span></span>

1.  <span data-ttu-id="cb0f9-164">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="cb0f9-165">Откроется окно свойств для приложения.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-165">The properties window for the application is displayed.</span></span>

2.  <span data-ttu-id="cb0f9-166">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="cb0f9-166">Click the **Application** tab.</span></span>

3.  <span data-ttu-id="cb0f9-167">В **требуемой версии .NET framework** выберите [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb0f9-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cb0f9-168">(Не выбирайте **клиентский профиль .NET Framework 4**.)</span><span class="sxs-lookup"><span data-stu-id="cb0f9-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4.  <span data-ttu-id="cb0f9-169">Добавьте ссылку на сборку кэширования, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-169">Add a reference to the caching assembly by following these steps:</span></span>

    1.  <span data-ttu-id="cb0f9-170">Щелкните правой кнопкой мыши **ссылки** папку и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2.  <span data-ttu-id="cb0f9-171">Выберите **.NET** выберите `System.Runtime.Caching`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="cb0f9-172">Добавление кнопки в окне WPF</span><span class="sxs-lookup"><span data-stu-id="cb0f9-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="cb0f9-173">Затем добавьте элемент управления button и создайте обработчик событий для кнопки `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="cb0f9-174">Позже будет добавлен код, поэтому при нажатии кнопки, кэшируются и отображается содержимое текстового файла.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="cb0f9-175">Чтобы добавить элемент управления button</span><span class="sxs-lookup"><span data-stu-id="cb0f9-175">To add a button control</span></span>

1.  <span data-ttu-id="cb0f9-176">В **обозревателе решений**, дважды щелкните файл MainWindow.xaml, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2.  <span data-ttu-id="cb0f9-177">Из **элементов**в разделе **стандартных элементов управления WPF**, перетащите `Button` управления `MainWindow` окна.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3.  <span data-ttu-id="cb0f9-178">В **свойства** окне `Content` свойство `Button` управления **получить кэш**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="cb0f9-179">Инициализация кэша и кэширование записи</span><span class="sxs-lookup"><span data-stu-id="cb0f9-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="cb0f9-180">Далее добавим код для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-180">Next, you will add the code to perform the following tasks:</span></span>

-   <span data-ttu-id="cb0f9-181">Создайте экземпляр класса кэша — то есть будет создавать новый <xref:System.Runtime.Caching.MemoryCache> объекта.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

-   <span data-ttu-id="cb0f9-182">Укажите, что кэш использует <xref:System.Runtime.Caching.HostFileChangeMonitor> объектов для отслеживания изменений в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

-   <span data-ttu-id="cb0f9-183">Чтение текстового файла и кэшировать его содержимое в качестве записи кэша.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-183">Read the text file and cache its contents as a cache entry.</span></span>

-   <span data-ttu-id="cb0f9-184">Отображение содержимого кэшированного текстового файла.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="cb0f9-185">Чтобы создать объект кэша</span><span class="sxs-lookup"><span data-stu-id="cb0f9-185">To create the cache object</span></span>

1.  <span data-ttu-id="cb0f9-186">Дважды щелкните кнопку, которую вы только что добавили для создания обработчика событий в файле MainWindow.xaml.cs или MainWindow.Xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2.  <span data-ttu-id="cb0f9-187">В верхней части файла (перед объявлением класса), добавьте следующий код `Imports` (Visual Basic) или `using` операторы (C#):</span><span class="sxs-lookup"><span data-stu-id="cb0f9-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3.  <span data-ttu-id="cb0f9-188">В обработчике событий добавьте следующий код для создания экземпляра объекта кэша:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="cb0f9-189"><xref:System.Runtime.Caching.ObjectCache> Класс является встроенный класс, который предоставляет кэш в памяти объект.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4.  <span data-ttu-id="cb0f9-190">Добавьте следующий код для чтения содержимого записи кэша с именем `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5.  <span data-ttu-id="cb0f9-191">Добавьте следующий код для проверки, является ли запись кэша с именем `filecontents` существует:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="cb0f9-192">Если указанная запись кэша не существует, необходимо прочитать текстовый файл и добавить его в качестве записи кэша в кэш.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6.  <span data-ttu-id="cb0f9-193">В `if/then` block, добавьте следующий код для создания нового <xref:System.Runtime.Caching.CacheItemPolicy> , указывающий, что срок действия записи кэша истекает через 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="cb0f9-194">Если нет сведений о удаления или истечения срока действия, по умолчанию используется <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, означающее записей кэша, которые никогда не истекать только по абсолютным временем.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="cb0f9-195">Вместо этого записей кэша истекает только в том случае, если имеется достаточный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="cb0f9-196">Рекомендуется следует всегда явно задавать абсолютный или скользящий срок действия.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>

7.  <span data-ttu-id="cb0f9-197">Внутри `if/then` блокировать и после кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы создать коллекцию для пути к файлам, которые необходимо отслеживать, а также, добавляемый в коллекцию путь файла текста:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="cb0f9-198">Если текстовый файл, вы хотите использовать не `c:\cache\cacheText.txt`, укажите путь, где вы хотите использовать текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8.  <span data-ttu-id="cb0f9-199">После кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы добавить новый <xref:System.Runtime.Caching.HostFileChangeMonitor> отслеживает объект в коллекцию изменение для записи кэша:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="cb0f9-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> Объект отслеживает путь файла текста и уведомляет кэш в том случае, если происходят изменения.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="cb0f9-201">В этом примере запись кэша истекает при изменении содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="cb0f9-202">После кода, добавленного на предыдущем шаге добавьте следующий код для считывания содержимого текстового файла:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="cb0f9-203">Отметка даты и времени добавляется таким образом, можно видеть, по истечении срока действия записи кэша.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="cb0f9-204">После кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы вставить содержимое файла в объект кэша в качестве <xref:System.Runtime.Caching.CacheItem> экземпляр:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="cb0f9-205">Укажите сведения о способе записи кэша, передав <xref:System.Runtime.Caching.CacheItemPolicy> объект, созданный ранее в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="cb0f9-206">После `if/then` block, добавьте следующий код для отображения содержимого кэшированного файла в окне сообщения:</span><span class="sxs-lookup"><span data-stu-id="cb0f9-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="cb0f9-207">В **построения** меню, щелкните **построения WPFCaching** для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="cb0f9-208">Проверка кэширования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="cb0f9-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="cb0f9-209">Теперь можно протестировать приложение.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="cb0f9-210">Проверка кэширования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="cb0f9-210">To test caching in the WPF application</span></span>

1.  <span data-ttu-id="cb0f9-211">Нажмите CTRL+F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="cb0f9-212">`MainWindow` Откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-212">The `MainWindow` window is displayed.</span></span>

2.  <span data-ttu-id="cb0f9-213">Нажмите кнопку **получить кэш**.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="cb0f9-214">Кэшированное содержимое из текстового файла отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="cb0f9-215">Обратите внимание, что отметка времени на файл.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-215">Notice the timestamp on the file.</span></span>

3.  <span data-ttu-id="cb0f9-216">Закройте окно сообщения и нажмите кнопку **получить кэш** снова **.**</span><span class="sxs-lookup"><span data-stu-id="cb0f9-216">Close the message box and then click **Get Cache** again **.**</span></span>

     <span data-ttu-id="cb0f9-217">Метка времени не изменяется.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-217">The timestamp is unchanged.</span></span> <span data-ttu-id="cb0f9-218">Это означает, что отображается кэшированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-218">This indicates the cached content is displayed.</span></span>

4.  <span data-ttu-id="cb0f9-219">Подождите 10 секунд или более, а затем нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="cb0f9-220">Это время отображается новой метки времени.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="cb0f9-221">Это означает, что политики сообщите кэша истек и что отображается новое кэшированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5.  <span data-ttu-id="cb0f9-222">В текстовом редакторе откройте текстовый файл, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="cb0f9-223">Еще не следует вносить любые изменения.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-223">Do not make any changes yet.</span></span>

6.  <span data-ttu-id="cb0f9-224">Закройте окно сообщения и нажмите кнопку **получить кэш** снова **.**</span><span class="sxs-lookup"><span data-stu-id="cb0f9-224">Close the message box and then click **Get Cache** again **.**</span></span>

     <span data-ttu-id="cb0f9-225">Обратите внимание, что отметка времени еще раз.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-225">Notice the timestamp again.</span></span>

7.  <span data-ttu-id="cb0f9-226">Внести изменения в текстовый файл и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-226">Make a change to the text file and then save the file.</span></span>

8.  <span data-ttu-id="cb0f9-227">Закройте окно сообщения и нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="cb0f9-228">Это окно сообщения содержит обновленное содержимое из текстового файла и новой метки времени.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="cb0f9-229">Это означает, что монитор изменений файла узла удалил запись кэша сразу после внесения изменений файл, несмотря на то, что не истек абсолютный период.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="cb0f9-230">Можно увеличить время вытеснения, в 20 секунд или более, чтобы предоставить больше времени для внесения изменений в файле.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="cb0f9-231">Пример кода</span><span class="sxs-lookup"><span data-stu-id="cb0f9-231">Code Example</span></span>
 <span data-ttu-id="cb0f9-232">После завершения этого пошагового руководства, код для созданного проекта будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cb0f9-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="cb0f9-233">См. также</span><span class="sxs-lookup"><span data-stu-id="cb0f9-233">See Also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="cb0f9-234">Кэширование в приложениях платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cb0f9-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)