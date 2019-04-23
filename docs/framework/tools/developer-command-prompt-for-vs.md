---
title: Командная строка разработчика для Visual Studio
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc88106a54a00b4b12e5043da7961791a98102c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344368"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="7e11d-102">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7e11d-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="7e11d-103">Командная строка разработчика для Visual Studio облегчает использование средств .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e11d-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="7e11d-104">Также эта командная строка автоматически задает определенные переменные среды.</span><span class="sxs-lookup"><span data-stu-id="7e11d-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="7e11d-105">Скачать Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="7e11d-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="7e11d-106">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="7e11d-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="7e11d-107">В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься несколько вариантов командной строки.</span><span class="sxs-lookup"><span data-stu-id="7e11d-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="7e11d-108">Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки.</span><span class="sxs-lookup"><span data-stu-id="7e11d-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="7e11d-109">(32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно попробовать [найти файлы на компьютере вручную](#manually-locate-the-files-on-your-machine) или [запустить командную строку из Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7e11d-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="7e11d-110">В Windows 10</span><span class="sxs-lookup"><span data-stu-id="7e11d-110">In Windows 10</span></span>

1. <span data-ttu-id="7e11d-111">В поле поиска на панели задач начните вводить имя средства, например `dev` или `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="7e11d-112">Откроется список установленных приложений, которые соответствуют вашему шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="7e11d-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="7e11d-113">Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="7e11d-114">Выберите пункт **Командная строка разработчика для Visual Studio** (или нужную вам командную строку).</span><span class="sxs-lookup"><span data-stu-id="7e11d-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="7e11d-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7e11d-115">In Windows 8.1</span></span>

1. <span data-ttu-id="7e11d-116">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="7e11d-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="7e11d-117">На **начальном экране** нажмите **CTRL**+**TAB**, чтобы открыть список **приложений**, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-117">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="7e11d-118">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e11d-118">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="7e11d-119">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="7e11d-119">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="7e11d-120">Windows 8</span><span class="sxs-lookup"><span data-stu-id="7e11d-120">In Windows 8</span></span>

1. <span data-ttu-id="7e11d-121">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="7e11d-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="7e11d-122">На **начальном экране** нажмите на клавиатуре клавишу с логотипом Windows![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-122">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="7e11d-123">Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-123">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="7e11d-124">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e11d-124">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="7e11d-125">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="7e11d-125">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="7e11d-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="7e11d-126">In Windows 7</span></span>

1. <span data-ttu-id="7e11d-127">В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7e11d-127">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="7e11d-128">В зависимости от установленной версии Visual Studio выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="7e11d-128">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="7e11d-129">Если установлен пакет SDK, например [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущие версии](https://developer.microsoft.com/windows/downloads/sdk-archive), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64.</span><span class="sxs-lookup"><span data-stu-id="7e11d-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="7e11d-130">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="7e11d-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="7e11d-131">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="7e11d-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="7e11d-132">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="7e11d-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="7e11d-133">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7e11d-133">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="7e11d-134">Попробуйте ввести имя файла командной строки, например *VsDevCmd.bat*, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (точный путь зависит от версии, выпуска и расположения установки Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="7e11d-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="7e11d-135">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7e11d-135">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="7e11d-136">Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню **Инструменты** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e11d-136">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="7e11d-137">Чтобы сделать средство доступным, добавьте его в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="7e11d-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="7e11d-138">Ниже приведены инструкции.</span><span class="sxs-lookup"><span data-stu-id="7e11d-138">Here are the steps:</span></span>

1. <span data-ttu-id="7e11d-139">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e11d-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="7e11d-140">Выберите меню **Инструменты** и затем выберите в нем пункт **Внешние инструменты**.</span><span class="sxs-lookup"><span data-stu-id="7e11d-140">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="7e11d-141">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7e11d-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="7e11d-142">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="7e11d-142">A new entry appears.</span></span>

4. <span data-ttu-id="7e11d-143">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="7e11d-144">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="7e11d-144">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="7e11d-145">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (эта команда запускает командную строку разработчика, установленную с Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="7e11d-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="7e11d-146">Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e11d-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="7e11d-147">Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.</span><span class="sxs-lookup"><span data-stu-id="7e11d-147">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="7e11d-148">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="7e11d-148">Choose the **OK** button.</span></span>

   <span data-ttu-id="7e11d-149">Новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="7e11d-149">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Пункт меню "Командная строка" в Visual Studio](media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="7e11d-151">См. также</span><span class="sxs-lookup"><span data-stu-id="7e11d-151">See also</span></span>

- [<span data-ttu-id="7e11d-152">Инструменты</span><span class="sxs-lookup"><span data-stu-id="7e11d-152">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="7e11d-153">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="7e11d-153">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
