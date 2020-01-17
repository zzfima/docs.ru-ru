---
title: Командная строка разработчика для Visual Studio
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: f028281d477284acf3ac4dac63f5ddbbd79f5259
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715828"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="37d75-102">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37d75-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="37d75-103">Командная строка разработчика для Visual Studio облегчает использование средств .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37d75-103">Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="37d75-104">Это командная строка, которая автоматически устанавливает определенные переменные среды.</span><span class="sxs-lookup"><span data-stu-id="37d75-104">It's a command prompt that automatically sets specific environment variables.</span></span> <span data-ttu-id="37d75-105">После открытия Командной строки разработчика, вы можете ввести команды для [средств платформы .NET Framework](index.md), например `ildasm` или `clrver`.</span><span class="sxs-lookup"><span data-stu-id="37d75-105">After opening Developer Command Prompt, you can enter the commands for [.NET Framework tools](index.md) such as `ildasm` or `clrver`.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37d75-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="37d75-106">Prerequisites</span></span>

- [<span data-ttu-id="37d75-107">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="37d75-107">Visual Studio 2019</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="37d75-108">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="37d75-108">Search for the command prompt on your machine</span></span>

<span data-ttu-id="37d75-109">В зависимости от версии Visual Studio, дополнительно установленных пакетов SDK и рабочих нагрузок может иметься несколько вариантов командных строк.</span><span class="sxs-lookup"><span data-stu-id="37d75-109">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs and workloads you've installed.</span></span> <span data-ttu-id="37d75-110">Если приведенные ниже действия не работают, можно попробовать [найти файлы на компьютере вручную](#manually-locate-the-files-on-your-machine) или [запустить командную строку из Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="37d75-110">If the following steps don't work, you can try to [manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [start the command prompt from inside Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="windows-10"></a><span data-ttu-id="37d75-111">Windows 10</span><span class="sxs-lookup"><span data-stu-id="37d75-111">Windows 10</span></span>

1. <span data-ttu-id="37d75-112">Выберите **Пуск** ![клавишу с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="37d75-112">Select **Start** ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="37d75-113">и прокрутите до буквы **V**.</span><span class="sxs-lookup"><span data-stu-id="37d75-113">and scroll to the letter **V**.</span></span>

1. <span data-ttu-id="37d75-114">Разверните папку **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="37d75-114">Expand the **Visual Studio 2019** folder.</span></span>

1. <span data-ttu-id="37d75-115">Выберите элемент **Командная строка разработчика для VS 2019** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="37d75-115">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

   <span data-ttu-id="37d75-116">Или вы можете начать вводить имя командной строки в поле поиска на панели задач и выбрать нужный результат, поскольку список результатов начнет отображать найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="37d75-116">Alternatively, you can start typing the name of the command prompt in the search box on the taskbar, and choose the result you want as the result list starts to display the search matches.</span></span>

   ![GIF с анимацией, показывающий поведение поиска в Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a><span data-ttu-id="37d75-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="37d75-118">Windows 8.1</span></span>

1. <span data-ttu-id="37d75-119">Перейдите на экран **Пуск**, нажав клавишу с логотипом Windows ![Клавиша с логотипом Windows на клавиатуре.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="37d75-119">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="37d75-120">на клавиатуре, например.</span><span class="sxs-lookup"><span data-stu-id="37d75-120">on your keyboard for example.</span></span>

1. <span data-ttu-id="37d75-121">На **начальном экране** нажмите **Ctrl**+**Tab**, чтобы открыть список **приложений**, а затем нажмите **V**. Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37d75-121">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then press **V**. This brings up a list that includes all installed Visual Studio command prompts.</span></span>

1. <span data-ttu-id="37d75-122">Выберите элемент **Командная строка разработчика для VS 2019** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="37d75-122">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

### <a name="windows-7"></a><span data-ttu-id="37d75-123">Windows 7</span><span class="sxs-lookup"><span data-stu-id="37d75-123">Windows 7</span></span>

1. <span data-ttu-id="37d75-124">Выберите **Пуск** а затем разверните **Все программы**.</span><span class="sxs-lookup"><span data-stu-id="37d75-124">Choose **Start** and then expand **All Programs**.</span></span>

1. <span data-ttu-id="37d75-125">Выберите **Visual Studio 2019** > **Инструменты Visual Studio** > **Командная строка разработчика для VS 2019**, или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="37d75-125">Choose **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt for VS 2019**, or the command prompt you want to use.</span></span>

   ![Меню "Пуск" в Windows 7 с выделенной командной строкой](./media/developer-command-prompt-for-vs/windows7-menu.png)

<span data-ttu-id="37d75-127">Если установлены другие пакеты SDK, например, [пакет SDK для Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) или [предыдущих версий](https://developer.microsoft.com/windows/downloads/sdk-archive), могут появиться дополнительные командные строки.</span><span class="sxs-lookup"><span data-stu-id="37d75-127">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts.</span></span> <span data-ttu-id="37d75-128">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="37d75-128">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="37d75-129">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="37d75-129">Manually locate the files on your machine</span></span>

<span data-ttu-id="37d75-130">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span><span class="sxs-lookup"><span data-stu-id="37d75-130">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span></span> <span data-ttu-id="37d75-131">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере.</span><span class="sxs-lookup"><span data-stu-id="37d75-131">But if, for some reason, searching for the command prompt doesn't produce the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="37d75-132">Попробуйте найти имя файла командной строки, например, *VsDevCmd.bat*или перейдите в папку "Инструменты", например, *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (путь изменяется в соответствии с версией Visual Studio, выпуском и расположением установки).</span><span class="sxs-lookup"><span data-stu-id="37d75-132">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder, such as *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="start-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="37d75-133">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37d75-133">Start the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="37d75-134">Для более удобного доступа Командную строку разработчика или любую другую командную строку можно добавить в меню "Инструменты" в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37d75-134">For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio.</span></span> <span data-ttu-id="37d75-135">Чтобы сделать средство доступным, добавьте его в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="37d75-135">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="37d75-136">Ниже приведены инструкции.</span><span class="sxs-lookup"><span data-stu-id="37d75-136">Here are the steps:</span></span>

1. <span data-ttu-id="37d75-137">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37d75-137">Open Visual Studio.</span></span>

1. <span data-ttu-id="37d75-138">В начальном окне выберите **Продолжить без кода**.</span><span class="sxs-lookup"><span data-stu-id="37d75-138">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="37d75-139">В строке меню, выберите **Инструменты** > **Внешние Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="37d75-139">On the menu bar, choose **Tools** > **External Tools**.</span></span>

1. <span data-ttu-id="37d75-140">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="37d75-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="37d75-141">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="37d75-141">A new entry appears.</span></span>

1. <span data-ttu-id="37d75-142">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="37d75-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

1. <span data-ttu-id="37d75-143">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="37d75-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

1. <span data-ttu-id="37d75-144">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span><span class="sxs-lookup"><span data-stu-id="37d75-144">In the **Arguments** field, specify where to find the specific command prompt you want to use, such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span></span> <span data-ttu-id="37d75-145">Эта команда запускает Командную строку разработчика, установленную вместе с Visual Studio 2019 Community.</span><span class="sxs-lookup"><span data-stu-id="37d75-145">This command launches the Developer Command Prompt that's installed with Visual Studio 2019 Community.</span></span> <span data-ttu-id="37d75-146">Измените это значение в соответствии с вашей версией, выпуском и расположением установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37d75-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

1. <span data-ttu-id="37d75-147">В поле **Исходный каталог** укажите каталог, в котором будет запускаться командная строка.</span><span class="sxs-lookup"><span data-stu-id="37d75-147">In the **Initial directory** field, specify the directory in which the command prompt will start.</span></span> <span data-ttu-id="37d75-148">Выберите значение, например **Каталог проекта**, нажав стрелку рядом с полем.</span><span class="sxs-lookup"><span data-stu-id="37d75-148">Choose a value such as **Project Directory** by selecting the arrow next to the field.</span></span>

1. <span data-ttu-id="37d75-149">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="37d75-149">Choose the **OK** button.</span></span>

   ![Диалоговое окно "Внешние инструменты" с заполненными значениями полей.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   <span data-ttu-id="37d75-151">В меню добавляется новый пункт и командную строку можно вызвать из меню "Инструменты".</span><span class="sxs-lookup"><span data-stu-id="37d75-151">The new menu item is added, and you can access the command prompt from the Tools menu.</span></span>

   ![Пункт меню "Командная строка" в Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="37d75-153">См. также</span><span class="sxs-lookup"><span data-stu-id="37d75-153">See also</span></span>

- [<span data-ttu-id="37d75-154">Инструменты .NET Framework</span><span class="sxs-lookup"><span data-stu-id="37d75-154">.NET Framework Tools</span></span>](index.md)
- [<span data-ttu-id="37d75-155">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="37d75-155">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
- [<span data-ttu-id="37d75-156">Использование набора инструментов C++ Microsoft из командной строки</span><span class="sxs-lookup"><span data-stu-id="37d75-156">Use the Microsoft C++ toolset from the command line</span></span>](/cpp/build/building-on-the-command-line)
