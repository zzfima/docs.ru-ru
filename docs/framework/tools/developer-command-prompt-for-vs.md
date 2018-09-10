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
ms.openlocfilehash: 4c95074190419dd3e984c7659ede917b83b97f08
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524720"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="1df8b-102">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1df8b-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="1df8b-103">Командная строка разработчика для Visual Studio автоматически задает переменные среды, с помощью которых можно легко использовать средства .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1df8b-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span>

> [!div class="button"]
[<span data-ttu-id="1df8b-104">Скачать Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="1df8b-104">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="1df8b-105">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="1df8b-105">Searching for the command prompt on your machine</span></span>

<span data-ttu-id="1df8b-106">В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься несколько вариантов командной строки.</span><span class="sxs-lookup"><span data-stu-id="1df8b-106">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="1df8b-107">Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки.</span><span class="sxs-lookup"><span data-stu-id="1df8b-107">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="1df8b-108">(32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно выполнить [Поиск файлов на компьютере вручную](#manually-locating-the-files-on-your-machine) или [Запуск командной строки из Visual Studio](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="1df8b-108">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running the command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="1df8b-109">В Windows 10</span><span class="sxs-lookup"><span data-stu-id="1df8b-109">In Windows 10</span></span>

1. <span data-ttu-id="1df8b-110">В поле поиска на панели задач начните вводить имя средства, например `dev` или `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-110">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="1df8b-111">Откроется список установленных приложений, которые соответствуют вашему шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="1df8b-111">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="1df8b-112">Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-112">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="1df8b-113">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="1df8b-113">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="1df8b-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1df8b-114">In Windows 8.1</span></span>

1. <span data-ttu-id="1df8b-115">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="1df8b-115">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="1df8b-116">На **начальном экране** нажмите `CTRL + TAB`, чтобы открыть список **приложений**, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-116">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="1df8b-117">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1df8b-117">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="1df8b-118">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="1df8b-118">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="1df8b-119">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1df8b-119">In Windows 8</span></span>

1. <span data-ttu-id="1df8b-120">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="1df8b-120">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="1df8b-121">На **начальном экране** нажмите на клавиатуре клавишу с логотипом Windows![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-121">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="1df8b-122">Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-122">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="1df8b-123">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1df8b-123">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="1df8b-124">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="1df8b-124">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="1df8b-125">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1df8b-125">In Windows 7</span></span>

1. <span data-ttu-id="1df8b-126">В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="1df8b-126">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="1df8b-127">В зависимости от установленной версии Visual Studio выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="1df8b-127">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="1df8b-128">Если установлен пакет SDK, например [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущие версии](https://developer.microsoft.com/windows/downloads/sdk-archive), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64.</span><span class="sxs-lookup"><span data-stu-id="1df8b-128">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="1df8b-129">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="1df8b-129">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="1df8b-130">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="1df8b-130">Manually locate the files on your machine</span></span>

<span data-ttu-id="1df8b-131">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="1df8b-131">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="1df8b-132">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1df8b-132">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="1df8b-133">Попробуйте ввести имя файла командной строки, например *VsDevCmd.bat*, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (точный путь зависит от версии, выпуска и расположения установки Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="1df8b-133">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="1df8b-134">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1df8b-134">Run command prompt from inside Visual Studio</span></span>

<span data-ttu-id="1df8b-135">Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню **Инструменты** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1df8b-135">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="1df8b-136">Чтобы сделать средство доступным, добавьте его в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="1df8b-136">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="1df8b-137">Ниже приведены инструкции.</span><span class="sxs-lookup"><span data-stu-id="1df8b-137">Here are the steps:</span></span>

1. <span data-ttu-id="1df8b-138">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1df8b-138">Open Visual Studio.</span></span>

2. <span data-ttu-id="1df8b-139">Выберите меню **Инструменты** и затем выберите в нем пункт **Внешние инструменты**.</span><span class="sxs-lookup"><span data-stu-id="1df8b-139">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="1df8b-140">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1df8b-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="1df8b-141">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="1df8b-141">A new entry appears.</span></span>

4. <span data-ttu-id="1df8b-142">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="1df8b-143">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="1df8b-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="1df8b-144">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (эта команда запускает командную строку разработчика, установленную с Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="1df8b-144">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="1df8b-145">Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1df8b-145">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="1df8b-146">Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.</span><span class="sxs-lookup"><span data-stu-id="1df8b-146">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="1df8b-147">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="1df8b-147">Choose the **OK** button.</span></span>

   <span data-ttu-id="1df8b-148">Новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="1df8b-148">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="1df8b-149">См. также</span><span class="sxs-lookup"><span data-stu-id="1df8b-149">See also</span></span>

- [<span data-ttu-id="1df8b-150">Инструменты</span><span class="sxs-lookup"><span data-stu-id="1df8b-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="1df8b-151">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="1df8b-151">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
