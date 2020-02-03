---
title: Кэширование данных приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: b7d999f94e2f2ae410a16e537d51c0f890def4e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728056"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="fa293-102">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="fa293-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="fa293-103">Кэширование позволяет хранить данные в памяти для быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="fa293-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="fa293-104">При повторном доступе к данным приложения могут получать их из кэша вместо извлечения из исходного источника.</span><span class="sxs-lookup"><span data-stu-id="fa293-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="fa293-105">Это может повысить производительность и масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="fa293-105">This can improve performance and scalability.</span></span> <span data-ttu-id="fa293-106">Кроме того, кэширование обеспечивает доступность данных при временной недоступности источника данных.</span><span class="sxs-lookup"><span data-stu-id="fa293-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="fa293-107">.NET Framework предоставляет классы, позволяющие использовать кэширование в приложениях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa293-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="fa293-108">Эти классы находятся в пространстве имен <xref:System.Runtime.Caching>.</span><span class="sxs-lookup"><span data-stu-id="fa293-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="fa293-109">Пространство имен <xref:System.Runtime.Caching> является новым в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fa293-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="fa293-110">Это пространство имен делает кэширование доступным для всех .NET Framework приложений.</span><span class="sxs-lookup"><span data-stu-id="fa293-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="fa293-111">В предыдущих версиях .NET Framework кэширование было доступно только в пространстве имен <xref:System.Web> и, следовательно, требовало зависимости от классов ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fa293-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="fa293-112">В этом пошаговом руководстве показано, как использовать функции кэширования, доступные в .NET Framework в составе [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="fa293-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fa293-113">В этом пошаговом руководстве вы кэшируете содержимое текстового файла.</span><span class="sxs-lookup"><span data-stu-id="fa293-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="fa293-114">В данном пошаговом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="fa293-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="fa293-115">Создание проекта приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="fa293-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="fa293-116">Добавление ссылки на .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fa293-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="fa293-117">Инициализация кэша.</span><span class="sxs-lookup"><span data-stu-id="fa293-117">Initializing a cache.</span></span>

- <span data-ttu-id="fa293-118">Добавление записи кэша, содержащей содержимое текстового файла.</span><span class="sxs-lookup"><span data-stu-id="fa293-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="fa293-119">Предоставление политики вытеснения для записи кэша.</span><span class="sxs-lookup"><span data-stu-id="fa293-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="fa293-120">Мониторинг пути к кэшированному файлу и уведомление экземпляра кэша об изменениях отслеживаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="fa293-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa293-121">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fa293-121">Prerequisites</span></span>
 <span data-ttu-id="fa293-122">Для выполнения задач этого руководства необходимы:</span><span class="sxs-lookup"><span data-stu-id="fa293-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="fa293-123">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="fa293-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="fa293-124">Текстовый файл, содержащий небольшой объем текста.</span><span class="sxs-lookup"><span data-stu-id="fa293-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="fa293-125">(Содержимое текстового файла будет отображаться в окне сообщения.) В коде, показанном в пошаговом руководстве, предполагается, что вы работаете со следующим файлом:</span><span class="sxs-lookup"><span data-stu-id="fa293-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="fa293-126">Однако можно использовать любой текстовый файл и внести небольшие изменения в код в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="fa293-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="fa293-127">Создание проекта приложения WPF</span><span class="sxs-lookup"><span data-stu-id="fa293-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="fa293-128">Сначала вы создадите проект приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="fa293-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="fa293-129">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="fa293-129">To create a WPF application</span></span>

1. <span data-ttu-id="fa293-130">Запустите среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa293-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="fa293-131">В меню **файл** выберите пункт **создать**, а затем щелкните **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="fa293-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="fa293-132">Откроется диалоговое окно **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="fa293-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="fa293-133">В разделе **Установленные шаблоны**выберите язык программирования, который необходимо использовать (**Visual Basic** или **Visual C#** ).</span><span class="sxs-lookup"><span data-stu-id="fa293-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="fa293-134">В диалоговом окне **Новый проект** выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="fa293-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa293-135">Если шаблон **приложения WPF** не отображается, убедитесь, что выбрана версия .NET Framework, поддерживающая WPF.</span><span class="sxs-lookup"><span data-stu-id="fa293-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="fa293-136">В диалоговом окне **Новый проект** выберите .NET Framework 4 из списка.</span><span class="sxs-lookup"><span data-stu-id="fa293-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="fa293-137">В текстовом поле **имя** введите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="fa293-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="fa293-138">Например, можно ввести **впфкачинг**.</span><span class="sxs-lookup"><span data-stu-id="fa293-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="fa293-139">Установите флажок **Создать каталог для решения**.</span><span class="sxs-lookup"><span data-stu-id="fa293-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="fa293-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa293-140">Click **OK**.</span></span>

     <span data-ttu-id="fa293-141">Конструктор WPF откроется в режиме **конструктора** и отобразит файл MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="fa293-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="fa293-142">Visual Studio создаст папку **My Project** , файл Application. XAML и файл MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="fa293-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="fa293-143">Нацеливание на .NET Framework и Добавление ссылки на сборки кэширования</span><span class="sxs-lookup"><span data-stu-id="fa293-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="fa293-144">По умолчанию приложения WPF ориентированы на клиентский профиль .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fa293-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="fa293-145">Чтобы использовать пространство имен <xref:System.Runtime.Caching> в приложении WPF, приложение должно быть предназначено для .NET Framework 4 (а не для клиентского профиля .NET Framework 4) и должно включать ссылку на пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fa293-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="fa293-146">Поэтому следующим шагом является изменение целевого объекта .NET Framework и Добавление ссылки на пространство имен <xref:System.Runtime.Caching>.</span><span class="sxs-lookup"><span data-stu-id="fa293-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="fa293-147">Процедура изменения целевого объекта .NET Framework отличается в проекте Visual Basic и в визуальном C# проекте.</span><span class="sxs-lookup"><span data-stu-id="fa293-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="fa293-148">Изменение целевого .NET Framework в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa293-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="fa293-149">В **обозревателе решений**щелкните правой кнопкой мыши имя проекта и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="fa293-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="fa293-150">Откроется окно свойств приложения.</span><span class="sxs-lookup"><span data-stu-id="fa293-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="fa293-151">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="fa293-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="fa293-152">В нижней части окна щелкните **Дополнительные параметры компиляции...** .</span><span class="sxs-lookup"><span data-stu-id="fa293-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="fa293-153">Откроется диалоговое окно **Дополнительные параметры компилятора** .</span><span class="sxs-lookup"><span data-stu-id="fa293-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="fa293-154">В списке **Целевая платформа (все конфигурации)** выберите .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fa293-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="fa293-155">(Не выбирайте .NET Framework 4-клиентский профиль.)</span><span class="sxs-lookup"><span data-stu-id="fa293-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="fa293-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa293-156">Click **OK**.</span></span>

     <span data-ttu-id="fa293-157">Откроется диалоговое окно **Изменение целевой рабочей среды**.</span><span class="sxs-lookup"><span data-stu-id="fa293-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="fa293-158">В диалоговом окне **Изменение целевой платформы** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="fa293-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="fa293-159">Проект будет закрыт и снова открыт.</span><span class="sxs-lookup"><span data-stu-id="fa293-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="fa293-160">Добавьте ссылку на сборку Caching, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa293-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="fa293-161">В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="fa293-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="fa293-162">Перейдите на вкладку **.NET** , выберите `System.Runtime.Caching`и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa293-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="fa293-163">Изменение целевого .NET Framework в визуальном C# проекте</span><span class="sxs-lookup"><span data-stu-id="fa293-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="fa293-164">В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="fa293-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="fa293-165">Откроется окно свойств приложения.</span><span class="sxs-lookup"><span data-stu-id="fa293-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="fa293-166">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="fa293-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="fa293-167">В списке **Целевая платформа** выберите .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fa293-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="fa293-168">(Не выбирайте **.NET Framework 4-клиентский профиль**.)</span><span class="sxs-lookup"><span data-stu-id="fa293-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="fa293-169">Добавьте ссылку на сборку Caching, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa293-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="fa293-170">Щелкните правой кнопкой мыши папку **ссылки** и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="fa293-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="fa293-171">Перейдите на вкладку **.NET** , выберите `System.Runtime.Caching`и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa293-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="fa293-172">Добавление кнопки в окно WPF</span><span class="sxs-lookup"><span data-stu-id="fa293-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="fa293-173">Далее предстоит добавить элемент управления Button и создать обработчик событий для `Click` события кнопки.</span><span class="sxs-lookup"><span data-stu-id="fa293-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="fa293-174">Позже вы добавите код, чтобы при нажатии кнопки содержимое текстового файла кэшируется и отображалось.</span><span class="sxs-lookup"><span data-stu-id="fa293-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="fa293-175">Добавление элемента управления "Кнопка"</span><span class="sxs-lookup"><span data-stu-id="fa293-175">To add a button control</span></span>

1. <span data-ttu-id="fa293-176">В **Обозреватель решений**дважды щелкните файл MainWindow. XAML, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="fa293-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="fa293-177">На **панели элементов**в разделе **Общие элементы управления WPF**перетащите элемент управления `Button` в окно `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="fa293-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="fa293-178">В окне **Свойства** задайте для свойства `Content` элемента управления `Button` значение **получить кэш**.</span><span class="sxs-lookup"><span data-stu-id="fa293-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="fa293-179">Инициализация кэша и кэширование записи</span><span class="sxs-lookup"><span data-stu-id="fa293-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="fa293-180">Далее предстоит добавить код для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="fa293-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="fa293-181">Создайте экземпляр класса Cache, то есть будет создан экземпляр нового объекта <xref:System.Runtime.Caching.MemoryCache>.</span><span class="sxs-lookup"><span data-stu-id="fa293-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="fa293-182">Укажите, что кэш использует объект <xref:System.Runtime.Caching.HostFileChangeMonitor> для отслеживания изменений в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="fa293-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="fa293-183">Чтение текстового файла и кэширование его содержимого в виде записи кэша.</span><span class="sxs-lookup"><span data-stu-id="fa293-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="fa293-184">Отображает содержимое кэшированного текстового файла.</span><span class="sxs-lookup"><span data-stu-id="fa293-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="fa293-185">Создание объекта Cache</span><span class="sxs-lookup"><span data-stu-id="fa293-185">To create the cache object</span></span>

1. <span data-ttu-id="fa293-186">Дважды щелкните только что добавленную кнопку, чтобы создать обработчик событий в файле MainWindow.xaml.cs или MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="fa293-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="fa293-187">В верхней части файла (перед объявлением класса) добавьте следующие операторы `Imports` (Visual Basic) или `using` (C#):</span><span class="sxs-lookup"><span data-stu-id="fa293-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="fa293-188">В обработчике событий добавьте следующий код для создания экземпляра объекта кэша:</span><span class="sxs-lookup"><span data-stu-id="fa293-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="fa293-189">Класс <xref:System.Runtime.Caching.ObjectCache> является встроенным классом, который предоставляет кэш объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="fa293-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="fa293-190">Добавьте следующий код для чтения содержимого записи кэша с именем `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="fa293-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="fa293-191">Добавьте следующий код, чтобы проверить, существует ли запись кэша с именем `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="fa293-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="fa293-192">Если указанная запись кэша не существует, необходимо прочитать текстовый файл и добавить его в кэш в качестве записи кэша.</span><span class="sxs-lookup"><span data-stu-id="fa293-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="fa293-193">В блоке `if/then` добавьте следующий код, чтобы создать новый объект <xref:System.Runtime.Caching.CacheItemPolicy>, указывающий, что срок действия записи кэша истекает через 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="fa293-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="fa293-194">Если сведения о вытеснении или истечении срока действия не указаны, значение по умолчанию — <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>. Это означает, что срок действия записей кэша никогда не истекает на основе только абсолютного времени.</span><span class="sxs-lookup"><span data-stu-id="fa293-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="fa293-195">Вместо этого срок действия записей кэша истекает только в случае нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="fa293-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="fa293-196">Рекомендуется всегда явно предоставлять либо абсолютный, либо скользящий срок действия.</span><span class="sxs-lookup"><span data-stu-id="fa293-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="fa293-197">В блоке `if/then` и после кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы создать коллекцию для путей к файлам, которые требуется отслеживать, а также для добавления пути к текстовому файлу в коллекцию:</span><span class="sxs-lookup"><span data-stu-id="fa293-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="fa293-198">Если нужный текстовый файл не `c:\cache\cacheText.txt`, укажите путь, по которому следует использовать текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fa293-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="fa293-199">После кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы добавить новый объект <xref:System.Runtime.Caching.HostFileChangeMonitor> в коллекцию мониторов изменений для записи кэша:</span><span class="sxs-lookup"><span data-stu-id="fa293-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="fa293-200">Объект <xref:System.Runtime.Caching.HostFileChangeMonitor> отслеживает путь к текстовому файлу и уведомляет кэш, если происходят изменения.</span><span class="sxs-lookup"><span data-stu-id="fa293-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="fa293-201">В этом примере срок действия записи кэша истечет при изменении содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="fa293-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="fa293-202">После кода, добавленного на предыдущем шаге, добавьте следующий код для чтения содержимого текстового файла:</span><span class="sxs-lookup"><span data-stu-id="fa293-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="fa293-203">Добавлена метка даты и времени, чтобы вы могли увидеть, когда истечет срок действия записи кэша.</span><span class="sxs-lookup"><span data-stu-id="fa293-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="fa293-204">После кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы вставить содержимое файла в объект кэша в качестве экземпляра <xref:System.Runtime.Caching.CacheItem>:</span><span class="sxs-lookup"><span data-stu-id="fa293-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="fa293-205">Укажите сведения о том, как запись кэша должна быть удалена путем передачи объекта <xref:System.Runtime.Caching.CacheItemPolicy>, созданного ранее в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="fa293-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="fa293-206">После блока `if/then` добавьте следующий код для вывода содержимого кэшированного файла в окне сообщения:</span><span class="sxs-lookup"><span data-stu-id="fa293-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="fa293-207">В меню **Сборка** выберите команду **построить впфкачинг** , чтобы выполнить сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="fa293-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="fa293-208">Тестирование кэширования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="fa293-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="fa293-209">Теперь можно протестировать приложение.</span><span class="sxs-lookup"><span data-stu-id="fa293-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="fa293-210">Тестирование кэширования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="fa293-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="fa293-211">Для запуска приложения нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="fa293-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="fa293-212">Откроется окно `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="fa293-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="fa293-213">Нажмите кнопку **получить кэш**.</span><span class="sxs-lookup"><span data-stu-id="fa293-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="fa293-214">Кэшированное содержимое из текстового файла отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="fa293-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="fa293-215">Обратите внимание на метку времени файла.</span><span class="sxs-lookup"><span data-stu-id="fa293-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="fa293-216">Закройте окно сообщения и нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="fa293-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="fa293-217">Метка времени не изменена.</span><span class="sxs-lookup"><span data-stu-id="fa293-217">The timestamp is unchanged.</span></span> <span data-ttu-id="fa293-218">Это означает, что отображается кэшированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="fa293-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="fa293-219">Подождите 10 секунд или более и нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="fa293-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="fa293-220">На этот раз отображается новая метка времени.</span><span class="sxs-lookup"><span data-stu-id="fa293-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="fa293-221">Это означает, что политика разрешит срок действия записи кэша и отобразится новое кэшированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="fa293-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="fa293-222">В текстовом редакторе откройте созданный текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fa293-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="fa293-223">Пока не вносите никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="fa293-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="fa293-224">Закройте окно сообщения и нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="fa293-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="fa293-225">Обратите внимание на метку времени.</span><span class="sxs-lookup"><span data-stu-id="fa293-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="fa293-226">Внесите изменения в текстовый файл, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="fa293-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="fa293-227">Закройте окно сообщения и нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="fa293-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="fa293-228">Это окно сообщения содержит обновленное содержимое из текстового файла и новую метку времени.</span><span class="sxs-lookup"><span data-stu-id="fa293-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="fa293-229">Это означает, что монитор изменений файлов узла удалил запись кэша сразу после изменения файла, несмотря на то, что истек период времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="fa293-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa293-230">Время вытеснения можно увеличить до 20 секунд или больше, чтобы больше времени можно было внести изменения в файл.</span><span class="sxs-lookup"><span data-stu-id="fa293-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="fa293-231">Пример кода</span><span class="sxs-lookup"><span data-stu-id="fa293-231">Code Example</span></span>
 <span data-ttu-id="fa293-232">После завершения этого пошагового руководства код для созданного проекта будет похож на следующий пример.</span><span class="sxs-lookup"><span data-stu-id="fa293-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="fa293-233">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fa293-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="fa293-234">Кэширование в приложениях платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa293-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
