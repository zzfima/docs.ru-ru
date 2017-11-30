---
title: "Пошаговое руководство. Кэширование данных приложения WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c04a2860b46460065a09de3dafedc7010753d36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="5f4ce-102">Пошаговое руководство. Кэширование данных приложения WPF</span><span class="sxs-lookup"><span data-stu-id="5f4ce-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="5f4ce-103">Кэширование позволяет хранить данные в памяти для быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="5f4ce-104">При повторном доступе к данным приложения могут получать данные из кэша вместо их извлечения из исходного источника.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="5f4ce-105">Это может повысить производительность и масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-105">This can improve performance and scalability.</span></span> <span data-ttu-id="5f4ce-106">Кроме того, кэширование обеспечивает доступность данных при временной недоступности источника данных.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>  
  
 <span data-ttu-id="5f4ce-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Предоставляет классы, которые позволяют использовать кэширование в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="5f4ce-108">Эти классы находятся в <xref:System.Runtime.Caching> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f4ce-109"><xref:System.Runtime.Caching> Пространство имен впервые появилось в [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="5f4ce-110">Это пространство имен обеспечивает кэширование доступно всем [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="5f4ce-111">В предыдущих версиях [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] кэширование было доступно только в пространстве имен <xref:System.Web> и поэтому требовало зависимости от классов ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>  
  
 <span data-ttu-id="5f4ce-112">В этом пошаговом руководстве демонстрируется использование функции кэширования, которая доступна в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] как часть [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="5f4ce-113">В этом руководстве кэширования содержимого текстового файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-113">In the walkthrough, you cache the contents of a text file.</span></span>  
  
 <span data-ttu-id="5f4ce-114">В данном пошаговом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-114">Tasks illustrated in this walkthrough include the following:</span></span>  
  
-   <span data-ttu-id="5f4ce-115">Создание проекта приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-115">Creating a WPF application project.</span></span>  
  
-   <span data-ttu-id="5f4ce-116">Добавление ссылки на [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="5f4ce-117">Инициализация кэша.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-117">Initializing a cache.</span></span>  
  
-   <span data-ttu-id="5f4ce-118">Добавление записи кэша, который содержит содержимое текстового файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-118">Adding a cache entry that contains the contents of a text file.</span></span>  
  
-   <span data-ttu-id="5f4ce-119">Определяет политику вытеснении для записи кэша.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-119">Providing an eviction policy for the cache entry.</span></span>  
  
-   <span data-ttu-id="5f4ce-120">Отслеживание пути к кэшированному файлу и уведомление экземпляра кэша об изменения отслеживаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5f4ce-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5f4ce-121">Prerequisites</span></span>  
 <span data-ttu-id="5f4ce-122">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="5f4ce-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="5f4ce-124">Текстовый файл, содержащий небольшой объем текста.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="5f4ce-125">(Содержимое текстового файла будет отображаться в окне сообщения.) Код, показанный в этом пошаговом руководстве предполагается, что вы работаете в следующем файле:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>  
  
     `c:\cache\cacheText.txt`  
  
     <span data-ttu-id="5f4ce-126">Тем не менее можно использовать любой текстовый файл и внести небольшие изменения в код в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>  
  
## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="5f4ce-127">Создание проекта приложения WPF</span><span class="sxs-lookup"><span data-stu-id="5f4ce-127">Creating a WPF Application Project</span></span>  
 <span data-ttu-id="5f4ce-128">Начнем с создания проекта приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-128">You will start by creating a WPF application project.</span></span>  
  
#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="5f4ce-129">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="5f4ce-129">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="5f4ce-130">Запустите [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-130">Start [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f4ce-131">В **файл** меню, нажмите кнопку **New**, а затем нажмите кнопку **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>  
  
     <span data-ttu-id="5f4ce-132">Откроется диалоговое окно **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-132">The **New Project** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="5f4ce-133">В разделе **установленные шаблоны**, выберите язык программирования, который вы хотите использовать (**Visual Basic** или **Visual C#**).</span><span class="sxs-lookup"><span data-stu-id="5f4ce-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>  
  
4.  <span data-ttu-id="5f4ce-134">В **новый проект** выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-134">In the **New Project** dialog box, select **WPF Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f4ce-135">Если вы не видите **приложение WPF** шаблона, убедитесь, что выбрана версия [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поддерживает WPF.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="5f4ce-136">В **новый проект** выберите [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] из списка.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>  
  
5.  <span data-ttu-id="5f4ce-137">В **имя** текста введите имя для проекта.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="5f4ce-138">Например, можно ввести **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-138">For example, you can enter **WPFCaching**.</span></span>  
  
6.  <span data-ttu-id="5f4ce-139">Выберите **создать каталог для решения** флажок.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-139">Select the **Create directory for solution** check box.</span></span>  
  
7.  <span data-ttu-id="5f4ce-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-140">Click **OK**.</span></span>  
  
     <span data-ttu-id="5f4ce-141">Откроется конструктор WPF в **разработки** просмотра и откроет файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="5f4ce-142">Создает **Мой проект** папку, файл Application.xaml и файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-142"> creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="5f4ce-143">Выбор целевой платформы .NET Framework и Добавление ссылки на сборки кэширования</span><span class="sxs-lookup"><span data-stu-id="5f4ce-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>  
 <span data-ttu-id="5f4ce-144">По умолчанию приложения WPF предназначены [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="5f4ce-145">Для использования <xref:System.Runtime.Caching> пространства имен в приложении WPF, приложение должно использовать [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (не [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) и должен включать ссылку на пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>  
  
 <span data-ttu-id="5f4ce-146">Таким образом, следующим шагом является изменение требуемой версии .NET Framework и добавьте ссылку на <xref:System.Runtime.Caching> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f4ce-147">Процедура изменения целевой версии .NET Framework отличается в проекте Visual Basic и в проекте Visual C#.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="5f4ce-148">Изменение целевой платформы .NET Framework в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f4ce-148">To change the target .NET Framework in Visual Basic</span></span>  
  
1.  <span data-ttu-id="5f4ce-149">В **обозревателя решений**, щелкните правой кнопкой мыши имя проекта и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="5f4ce-150">Откроется окно свойств для приложения.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-150">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="5f4ce-151">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-151">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="5f4ce-152">В нижней части окна, щелкните **Дополнительные параметры компиляции...** .</span><span class="sxs-lookup"><span data-stu-id="5f4ce-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>  
  
     <span data-ttu-id="5f4ce-153">**Дополнительные параметры компилятора** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="5f4ce-154">В **требуемая версия .NET framework (все конфигурации)** выберите [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="5f4ce-155">(Не выбирайте [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="5f4ce-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>  
  
5.  <span data-ttu-id="5f4ce-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-156">Click **OK**.</span></span>  
  
     <span data-ttu-id="5f4ce-157">**Изменение целевой рабочей среды** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-157">The **Target Framework Change** dialog box is displayed.</span></span>  
  
6.  <span data-ttu-id="5f4ce-158">В **Изменение целевой рабочей среды** диалоговое окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>  
  
     <span data-ttu-id="5f4ce-159">Проект будет закрыт и вновь открыт.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-159">The project is closed and is then reopened.</span></span>  
  
7.  <span data-ttu-id="5f4ce-160">Добавьте ссылку на сборку кэширования, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-160">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="5f4ce-161">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="5f4ce-162">Выберите **.NET** выберите `System.Runtime.Caching`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="5f4ce-163">Изменение целевой платформы .NET Framework в проекте Visual C#</span><span class="sxs-lookup"><span data-stu-id="5f4ce-163">To change the target .NET Framework in a Visual C# project</span></span>  
  
1.  <span data-ttu-id="5f4ce-164">В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>  
  
     <span data-ttu-id="5f4ce-165">Откроется окно свойств для приложения.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-165">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="5f4ce-166">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="5f4ce-166">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="5f4ce-167">В **требуемой версии .NET framework** выберите [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f4ce-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="5f4ce-168">(Не выбирайте **клиентский профиль .NET Framework 4**.)</span><span class="sxs-lookup"><span data-stu-id="5f4ce-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>  
  
4.  <span data-ttu-id="5f4ce-169">Добавьте ссылку на сборку кэширования, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-169">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="5f4ce-170">Щелкните правой кнопкой мыши **ссылки** папку и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-170">Right-click the **References** folder and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="5f4ce-171">Выберите **.NET** выберите `System.Runtime.Caching`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="5f4ce-172">Добавление кнопки в окне WPF</span><span class="sxs-lookup"><span data-stu-id="5f4ce-172">Adding a Button to the WPF Window</span></span>  
 <span data-ttu-id="5f4ce-173">Затем добавьте элемент управления button и создайте обработчик событий для кнопки `Click` событий.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="5f4ce-174">Позже будет добавлен код, поэтому при нажатии кнопки, кэширование и отображение содержимого текстового файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>  
  
#### <a name="to-add-a-button-control"></a><span data-ttu-id="5f4ce-175">Чтобы добавить элемент управления button</span><span class="sxs-lookup"><span data-stu-id="5f4ce-175">To add a button control</span></span>  
  
1.  <span data-ttu-id="5f4ce-176">В **обозревателе решений**, дважды щелкните файл MainWindow.xaml, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>  
  
2.  <span data-ttu-id="5f4ce-177">Из **элементов**в разделе **стандартных элементов управления WPF**, перетащите `Button` управления `MainWindow` окна.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>  
  
3.  <span data-ttu-id="5f4ce-178">В **свойства** задайте `Content` свойство `Button` управления **получить кэш**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="5f4ce-179">Идет инициализация кэш и кэширование записи</span><span class="sxs-lookup"><span data-stu-id="5f4ce-179">Initializing the Cache and Caching an Entry</span></span>  
 <span data-ttu-id="5f4ce-180">Далее вы добавите код для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-180">Next, you will add the code to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5f4ce-181">Создайте экземпляр класса кэша — то есть, будет создан экземпляр нового <xref:System.Runtime.Caching.MemoryCache> объекта.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>  
  
-   <span data-ttu-id="5f4ce-182">Укажите, что кэш использует <xref:System.Runtime.Caching.HostFileChangeMonitor> объектов для отслеживания изменений в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>  
  
-   <span data-ttu-id="5f4ce-183">Чтение текстового файла и кэширование его содержимого в виде записи кэша.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-183">Read the text file and cache its contents as a cache entry.</span></span>  
  
-   <span data-ttu-id="5f4ce-184">Отображение содержимого кэшированного текстового файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-184">Display the contents of the cached text file.</span></span>  
  
#### <a name="to-create-the-cache-object"></a><span data-ttu-id="5f4ce-185">Чтобы создать объект кэша</span><span class="sxs-lookup"><span data-stu-id="5f4ce-185">To create the cache object</span></span>  
  
1.  <span data-ttu-id="5f4ce-186">Дважды щелкните кнопку, которую вы только что добавили для создания обработчика событий в файле MainWindow.xaml.cs или MainWindow.Xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>  
  
2.  <span data-ttu-id="5f4ce-187">В верхней части файла (перед объявлением класса), добавьте следующий `Imports` (Visual Basic) или `using` операторы (C#):</span><span class="sxs-lookup"><span data-stu-id="5f4ce-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  <span data-ttu-id="5f4ce-188">В обработчике событий добавьте следующий код для создания экземпляра объекта кэша:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-188">In the event handler, add the following code to instantiate the cache object:</span></span>  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <span data-ttu-id="5f4ce-189"><xref:System.Runtime.Caching.ObjectCache> Класс является встроенный класс, который предоставляет кэш объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>  
  
4.  <span data-ttu-id="5f4ce-190">Добавьте следующий код для чтения содержимого записи кэша с именем `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  <span data-ttu-id="5f4ce-191">Добавьте следующий код, чтобы проверить, является ли запись кэша с именем `filecontents` существует:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     <span data-ttu-id="5f4ce-192">Если указанная запись кэша не существует, необходимо прочитать текстовый файл и добавить его в качестве записи кэша в кэш.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>  
  
6.  <span data-ttu-id="5f4ce-193">В `if/then` блока, добавьте следующий код для создания нового <xref:System.Runtime.Caching.CacheItemPolicy> , указывающий, что срок действия записи кэша истекает через 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     <span data-ttu-id="5f4ce-194">Если никакие сведения вытеснение или истечения срока действия, значение по умолчанию — <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, означающее записей кэша неограниченный срок действия на основе только абсолютные вовремя.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="5f4ce-195">Вместо этого записей кэша срока действия только в том случае, если не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="5f4ce-196">Рекомендуется следует всегда явно задавать абсолютный или скользящий срок действия.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>  
  
7.  <span data-ttu-id="5f4ce-197">Внутри `if/then` блокировку и после кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы создать коллекцию для пути к файлам, которые требуется отслеживать и добавьте путь к текстовому файлу в коллекцию:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5f4ce-198">Если вы хотите использовать текстовый файл не `c:\cache\cacheText.txt`, укажите путь, где вы хотите использовать текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>  
  
8.  <span data-ttu-id="5f4ce-199">После кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы добавить новый <xref:System.Runtime.Caching.HostFileChangeMonitor> отслеживает изменения в коллекцию для записи кэша:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <span data-ttu-id="5f4ce-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> Объект отслеживает путь к текстовому файлу и уведомляет кэш, если происходят изменения.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="5f4ce-201">В этом примере запись кэша истекает при изменении содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-201">In this example, the cache entry will expire if the content of the file changes.</span></span>  
  
9. <span data-ttu-id="5f4ce-202">После кода, добавленного на предыдущем шаге добавьте следующий код для считывания содержимого текстового файла:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     <span data-ttu-id="5f4ce-203">Отметка даты и времени будет добавлен, чтобы вы могли во время истечения срока действия записи кэша.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>  
  
10. <span data-ttu-id="5f4ce-204">После кода, добавленного на предыдущем шаге, добавьте следующий код, чтобы вставить содержимое файла в объект кэша в качестве <xref:System.Runtime.Caching.CacheItem> экземпляр:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     <span data-ttu-id="5f4ce-205">Укажите сведения о способе записи кэша, передав <xref:System.Runtime.Caching.CacheItemPolicy> объект, созданный ранее в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>  
  
11. <span data-ttu-id="5f4ce-206">После `if/then` блока, добавьте следующий код, чтобы отобразить кэшированное содержимое файла в окне сообщения:</span><span class="sxs-lookup"><span data-stu-id="5f4ce-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. <span data-ttu-id="5f4ce-207">В **построения** меню, нажмите кнопку **WPFCaching построения** для построения проекта.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>  
  
## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="5f4ce-208">Проверка кэширования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="5f4ce-208">Testing Caching in the WPF Application</span></span>  
 <span data-ttu-id="5f4ce-209">Теперь можно протестировать приложение.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-209">You can now test the application.</span></span>  
  
#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="5f4ce-210">Проверка кэширования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="5f4ce-210">To test caching in the WPF application</span></span>  
  
1.  <span data-ttu-id="5f4ce-211">Нажмите CTRL+F5, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-211">Press CTRL+F5 to run the application.</span></span>  
  
     <span data-ttu-id="5f4ce-212">`MainWindow` Откроется окно.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-212">The `MainWindow` window is displayed.</span></span>  
  
2.  <span data-ttu-id="5f4ce-213">Нажмите кнопку **получить кэш**.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-213">Click **Get Cache**.</span></span>  
  
     <span data-ttu-id="5f4ce-214">В окне сообщения отображается кэшированное содержимое из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="5f4ce-215">Обратите внимание, отметку времени для файла.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-215">Notice the timestamp on the file.</span></span>  
  
3.  <span data-ttu-id="5f4ce-216">Закрыть окно сообщения, а затем нажмите кнопку **получить кэш** снова**.**</span><span class="sxs-lookup"><span data-stu-id="5f4ce-216">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="5f4ce-217">Отметка времени не изменяется.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-217">The timestamp is unchanged.</span></span> <span data-ttu-id="5f4ce-218">Это означает, что отображается кэшированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-218">This indicates the cached content is displayed.</span></span>  
  
4.  <span data-ttu-id="5f4ce-219">Подождите 10 секунд или более, а затем нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="5f4ce-220">Это время будет отображаться новой метки времени.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="5f4ce-221">Указывает, разрешить, политика срока действия записи кэша и что отображается новое кэшированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>  
  
5.  <span data-ttu-id="5f4ce-222">В текстовом редакторе откройте текстовый файл, созданный вами.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="5f4ce-223">Пока не выполняйте изменения.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-223">Do not make any changes yet.</span></span>  
  
6.  <span data-ttu-id="5f4ce-224">Закрыть окно сообщения, а затем нажмите кнопку **получить кэш** снова**.**</span><span class="sxs-lookup"><span data-stu-id="5f4ce-224">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="5f4ce-225">Снова Обратите внимание отметка времени.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-225">Notice the timestamp again.</span></span>  
  
7.  <span data-ttu-id="5f4ce-226">Измените текстовый файл и сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-226">Make a change to the text file and then save the file.</span></span>  
  
8.  <span data-ttu-id="5f4ce-227">Закрыть окно сообщения, а затем нажмите кнопку **получить кэш** еще раз.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-227">Close the message box and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="5f4ce-228">Это окно сообщения содержит обновленное содержимое из текстового файла и новой метки времени.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="5f4ce-229">Это означает, что монитор изменений файла узла удалил запись кэша сразу после внесения изменений в файле, несмотря на то, что абсолютный период не истек.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f4ce-230">Можно увеличить время вытеснения 20 секунд или более, чтобы дать больше времени для внесения изменений в файле.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="5f4ce-231">Пример кода</span><span class="sxs-lookup"><span data-stu-id="5f4ce-231">Code Example</span></span>  
 <span data-ttu-id="5f4ce-232">После завершения данного пошагового руководства код для созданного проекта будет иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="5f4ce-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5f4ce-233">См. также</span><span class="sxs-lookup"><span data-stu-id="5f4ce-233">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [<span data-ttu-id="5f4ce-234">Кэширование в приложениях платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5f4ce-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
