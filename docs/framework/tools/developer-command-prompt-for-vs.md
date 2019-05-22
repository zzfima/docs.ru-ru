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
ms.openlocfilehash: 79cfc607e20d921c7ae942cb9755eee4264336eb
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877040"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="c8f7f-102">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c8f7f-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="c8f7f-103">Командная строка разработчика для Visual Studio облегчает использование средств .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="c8f7f-104">Также эта командная строка автоматически задает определенные переменные среды.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="c8f7f-105">Скачать Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="c8f7f-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="c8f7f-106">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="c8f7f-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="c8f7f-107">В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься несколько вариантов командной строки.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="c8f7f-108">Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="c8f7f-109">(32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно попробовать [найти файлы на компьютере вручную](#manually-locate-the-files-on-your-machine) или [запустить командную строку из Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c8f7f-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="c8f7f-110">В Windows 10</span><span class="sxs-lookup"><span data-stu-id="c8f7f-110">In Windows 10</span></span>

1. <span data-ttu-id="c8f7f-111">В поле поиска на панели задач начните вводить имя средства, например `dev` или `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="c8f7f-112">Откроется список установленных приложений, которые соответствуют вашему шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="c8f7f-113">Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="c8f7f-114">Выберите пункт **Командная строка разработчика для Visual Studio** (или нужную вам командную строку).</span><span class="sxs-lookup"><span data-stu-id="c8f7f-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="c8f7f-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c8f7f-115">In Windows 8.1</span></span>

1. <span data-ttu-id="c8f7f-116">Перейдите на экран **Пуск**, нажав клавишу с логотипом Windows ![Клавиша с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="c8f7f-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="c8f7f-117">на клавиатуре, например.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-117">on your keyboard for example.</span></span>

2. <span data-ttu-id="c8f7f-118">На **начальном экране** нажмите **CTRL**+**TAB**, чтобы открыть список **приложений**, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-118">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="c8f7f-119">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="c8f7f-120">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="c8f7f-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="c8f7f-121">Windows 8</span><span class="sxs-lookup"><span data-stu-id="c8f7f-121">In Windows 8</span></span>

1. <span data-ttu-id="c8f7f-122">Перейдите на экран **Пуск**, нажав клавишу с логотипом Windows ![Клавиша с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="c8f7f-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="c8f7f-123">на клавиатуре, например.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-123">on your keyboard for example.</span></span>

2. <span data-ttu-id="c8f7f-124">На экране **Пуск** нажмите клавишу с логотипом Windows ![Клавиша с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="c8f7f-124">On the **Start** screen, press the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="c8f7f-125">`+ Z`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-125">`+ Z`.</span></span>

3. <span data-ttu-id="c8f7f-126">Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-126">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="c8f7f-127">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-127">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="c8f7f-128">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="c8f7f-128">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="c8f7f-129">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c8f7f-129">In Windows 7</span></span>

1. <span data-ttu-id="c8f7f-130">В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-130">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="c8f7f-131">В зависимости от установленной версии Visual Studio выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-131">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="c8f7f-132">Если установлен пакет SDK, например [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущие версии](https://developer.microsoft.com/windows/downloads/sdk-archive), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-132">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="c8f7f-133">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-133">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="c8f7f-134">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="c8f7f-134">Manually locate the files on your machine</span></span>

<span data-ttu-id="c8f7f-135">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-135">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="c8f7f-136">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-136">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="c8f7f-137">Попробуйте ввести имя файла командной строки, например *VsDevCmd.bat*, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (точный путь зависит от версии, выпуска и расположения установки Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="c8f7f-137">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="c8f7f-138">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c8f7f-138">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="c8f7f-139">Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню **Инструменты** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-139">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="c8f7f-140">Чтобы сделать средство доступным, добавьте его в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-140">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="c8f7f-141">Ниже приведены инструкции.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-141">Here are the steps:</span></span>

1. <span data-ttu-id="c8f7f-142">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-142">Open Visual Studio.</span></span>

2. <span data-ttu-id="c8f7f-143">Выберите меню **Инструменты** и затем выберите в нем пункт **Внешние инструменты**.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-143">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="c8f7f-144">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-144">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="c8f7f-145">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-145">A new entry appears.</span></span>

4. <span data-ttu-id="c8f7f-146">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-146">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="c8f7f-147">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-147">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="c8f7f-148">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (эта команда запускает командную строку разработчика, установленную с Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="c8f7f-148">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="c8f7f-149">Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-149">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="c8f7f-150">Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-150">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="c8f7f-151">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="c8f7f-151">Choose the **OK** button.</span></span>

   <span data-ttu-id="c8f7f-152">Новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="c8f7f-152">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Пункт меню "Командная строка" в Visual Studio](media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="c8f7f-154">См. также</span><span class="sxs-lookup"><span data-stu-id="c8f7f-154">See also</span></span>

- [<span data-ttu-id="c8f7f-155">Инструменты</span><span class="sxs-lookup"><span data-stu-id="c8f7f-155">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="c8f7f-156">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="c8f7f-156">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
