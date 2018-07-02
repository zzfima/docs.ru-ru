---
title: Командная строка разработчика для Visual Studio
ms.date: 06/18/2018
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
ms.openlocfilehash: 8e64facffd4face929b28d660ffd5210f127c3bd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315229"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="acfdd-102">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="acfdd-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="acfdd-103">Командная строка разработчика для Visual Studio автоматически задает переменные среды, с помощью которых можно легко использовать средства .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="acfdd-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="acfdd-104">Командная строка разработчика устанавливается с полными выпусками и выпусками Community Edition Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="acfdd-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="acfdd-105">Она не устанавливается с версиями Visual Studio Express.</span><span class="sxs-lookup"><span data-stu-id="acfdd-105">It isn't installed with the Express versions of Visual Studio.</span></span>

> [!div class="button"]
[<span data-ttu-id="acfdd-106">Скачать Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="acfdd-106">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="acfdd-107">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="acfdd-107">Searching for the Command Prompt on your machine</span></span>

<span data-ttu-id="acfdd-108">В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься много вариантов командной строки.</span><span class="sxs-lookup"><span data-stu-id="acfdd-108">You may see many command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="acfdd-109">Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки.</span><span class="sxs-lookup"><span data-stu-id="acfdd-109">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="acfdd-110">(32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно выполнить [Поиск файлов на компьютере вручную](#manually-locating-the-files-on-your-machine) или [Запуск командной строки из Visual Studio](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="acfdd-110">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="acfdd-111">В Windows 10</span><span class="sxs-lookup"><span data-stu-id="acfdd-111">In Windows 10</span></span>

1. <span data-ttu-id="acfdd-112">В поле поиска на панели задач начните вводить имя средства, например `dev` или `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-112">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="acfdd-113">Откроется список установленных приложений, которые соответствуют вашему шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="acfdd-113">This brings a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="acfdd-114">Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="acfdd-115">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="acfdd-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="acfdd-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="acfdd-116">In Windows 8.1</span></span>

1. <span data-ttu-id="acfdd-117">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="acfdd-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="acfdd-118">На **начальном экране** нажмите `CTRL + TAB`, чтобы открыть список **приложений**, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="acfdd-119">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="acfdd-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="acfdd-120">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="acfdd-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="acfdd-121">Windows 8</span><span class="sxs-lookup"><span data-stu-id="acfdd-121">In Windows 8</span></span>

1. <span data-ttu-id="acfdd-122">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="acfdd-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="acfdd-123">На **начальном экране** нажмите на клавиатуре клавишу с логотипом Windows![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-123">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="acfdd-124">Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="acfdd-125">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="acfdd-125">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="acfdd-126">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="acfdd-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="acfdd-127">Windows 7</span><span class="sxs-lookup"><span data-stu-id="acfdd-127">In Windows 7</span></span>

1. <span data-ttu-id="acfdd-128">В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="acfdd-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="acfdd-129">В зависимости от установленной версии Visual Studio выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="acfdd-129">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="acfdd-130">Если установлен пакет SDK, например [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущие версии](https://developer.microsoft.com/windows/downloads/sdk-archive), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64.</span><span class="sxs-lookup"><span data-stu-id="acfdd-130">If you have other SDKs installed such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="acfdd-131">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="acfdd-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="acfdd-132">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="acfdd-132">Manually locating the files on your machine</span></span>

<span data-ttu-id="acfdd-133">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="acfdd-133">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="acfdd-134">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере.</span><span class="sxs-lookup"><span data-stu-id="acfdd-134">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="acfdd-135">Попробуйте ввести имя файла командной строки, например *VsDevCmd.bat*, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (точный путь зависит от версии, выпуска и расположения установки Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="acfdd-135">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="acfdd-136">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="acfdd-136">Running command prompt from inside Visual Studio</span></span>

<span data-ttu-id="acfdd-137">Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню "Инструменты" в Visual Studio, добавив ее в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="acfdd-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="acfdd-138">Вот как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="acfdd-138">This is how you can accomplish that:</span></span>

1. <span data-ttu-id="acfdd-139">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="acfdd-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="acfdd-140">Откройте меню **Инструменты** и выберите в нем пункт **Внешние инструменты**.</span><span class="sxs-lookup"><span data-stu-id="acfdd-140">Select the **Tools** menu and choose **External Tools**.</span></span>

3. <span data-ttu-id="acfdd-141">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="acfdd-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="acfdd-142">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="acfdd-142">A new entry appears.</span></span>

4. <span data-ttu-id="acfdd-143">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="acfdd-144">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="acfdd-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="acfdd-145">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (эта команда запускает командную строку разработчика, установленную с Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="acfdd-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="acfdd-146">Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="acfdd-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="acfdd-147">Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.</span><span class="sxs-lookup"><span data-stu-id="acfdd-147">Choose a value for the **Initial directory** field such as **Project Directory**.</span></span>

8. <span data-ttu-id="acfdd-148">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="acfdd-148">Choose the **OK** button.</span></span>

<span data-ttu-id="acfdd-149">После этого новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="acfdd-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="acfdd-150">См. также</span><span class="sxs-lookup"><span data-stu-id="acfdd-150">See also</span></span>

 [<span data-ttu-id="acfdd-151">Инструменты</span><span class="sxs-lookup"><span data-stu-id="acfdd-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="acfdd-152">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="acfdd-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)  
