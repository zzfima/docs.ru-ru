---
title: "Командная строка разработчика для Visual Studio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: 45
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0287c3f250a57f7a685191702be3ad5cc28fbec6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="5a71a-102">Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a71a-102">Developer Command Prompt for Visual Studio</span></span>
<span data-ttu-id="5a71a-103">Командная строка разработчика для Visual Studio автоматически задает переменные среды, с помощью которых можно легко использовать средства .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5a71a-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="5a71a-104">Командная строка разработчика устанавливается с полными выпусками и выпусками Community Edition Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5a71a-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="5a71a-105">Она не устанавливается с версиями Visual Studio Express.</span><span class="sxs-lookup"><span data-stu-id="5a71a-105">It is not installed with the Express versions of Visual Studio.</span></span>  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="5a71a-106">Поиск командной строки на компьютере</span><span class="sxs-lookup"><span data-stu-id="5a71a-106">Searching for the Command Prompt on your machine</span></span>  
 <span data-ttu-id="5a71a-107">В зависимости от версии Visual Studio и дополнительно установленных пакетов SDK может иметься несколько вариантов командной строки.</span><span class="sxs-lookup"><span data-stu-id="5a71a-107">You may see multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="5a71a-108">Например, в 64-разрядных версиях Visual Studio представлены 32-разрядная и 64-разрядная версии командной строки.</span><span class="sxs-lookup"><span data-stu-id="5a71a-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="5a71a-109">(32-разрядная и 64-разрядная версии большинства инструментов являются одинаковыми. Однако некоторые инструменты работают по-разному в 32-разрядных и 64-разрядных средах.) Если приведенные ниже действия не работают, можно выполнить [Поиск файлов на компьютере вручную](#alternative) или [Запуск командной строки из Visual Studio](#visualstudio).</span><span class="sxs-lookup"><span data-stu-id="5a71a-109">(The 32-bit and 64-bit versions of most tools are identical; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the steps below don't work, you can try [Manually locating the files on your machine](#alternative) or [Running command prompt from inside Visual Studio](#visualstudio).</span></span>  
  
 <span data-ttu-id="5a71a-110">**В Windows 10**</span><span class="sxs-lookup"><span data-stu-id="5a71a-110">**In Windows 10**</span></span>  
  
1.  <span data-ttu-id="5a71a-111">Откройте меню **Пуск**, например, нажав клавишу с логотипом Windows ![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="5a71a-111">Open the **Start** menu, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="5a71a-112">В меню **Пуск** введите `dev`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-112">On the **Start** menu, enter `dev`.</span></span> <span data-ttu-id="5a71a-113">Откроется список установленных приложений, которые соответствуют вашему шаблону поиска.</span><span class="sxs-lookup"><span data-stu-id="5a71a-113">This will bring a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="5a71a-114">Если вы ищете другую командную строку, попробуйте ввести другое условие поиска, например `prompt`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>  
  
3.  <span data-ttu-id="5a71a-115">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="5a71a-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="5a71a-116">**В Windows 8.1**</span><span class="sxs-lookup"><span data-stu-id="5a71a-116">**In Windows 8.1**</span></span>  
  
1.  <span data-ttu-id="5a71a-117">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="5a71a-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="5a71a-118">На **начальном экране** нажмите `CTRL + TAB`, чтобы открыть список **приложений**, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="5a71a-119">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5a71a-119">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
3.  <span data-ttu-id="5a71a-120">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="5a71a-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="5a71a-121">**В Windows 8**</span><span class="sxs-lookup"><span data-stu-id="5a71a-121">**In Windows 8**</span></span>  
  
1.  <span data-ttu-id="5a71a-122">Перейдите на **начальный** экран, например нажав клавишу с логотипом Windows ![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="5a71a-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="5a71a-123">На **начальном экране** нажмите на клавиатуре клавишу с логотипом Windows![логотип Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-123">On the **Start** screen, press the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>  
  
3.  <span data-ttu-id="5a71a-124">Выберите значок **представления "Приложения"** в нижней части экрана, а затем введите `V`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="5a71a-125">Появится список, включающий все установленные командные строки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5a71a-125">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
4.  <span data-ttu-id="5a71a-126">Выберите элемент **Командная строка разработчика** (или нужную командную строку).</span><span class="sxs-lookup"><span data-stu-id="5a71a-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="5a71a-127">**В Windows 7**</span><span class="sxs-lookup"><span data-stu-id="5a71a-127">**In Windows 7**</span></span>  
  
1.  <span data-ttu-id="5a71a-128">В меню **Пуск** разверните список **Все программы**, а затем папку **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="5a71a-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="5a71a-129">В зависимости от установленной версии Visual Studio, выберите пункт **Инструменты Visual Studio**, **Командная строка Visual Studio** или нужную командную строку.</span><span class="sxs-lookup"><span data-stu-id="5a71a-129">Depending on the version of Visual Studio you have installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>  
  
 <span data-ttu-id="5a71a-130">Если установлен [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) или [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk), в системе могут быть дополнительные командные строки для архитектур ARM, x86 или x64.</span><span class="sxs-lookup"><span data-stu-id="5a71a-130">If you have the [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) or [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="5a71a-131">Требуемая версия командной строки указана в документации по соответствующим инструментам.</span><span class="sxs-lookup"><span data-stu-id="5a71a-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="5a71a-132">Поиск файлов на компьютере вручную</span><span class="sxs-lookup"><span data-stu-id="5a71a-132">Manually locating the files on your machine</span></span>  
  <span data-ttu-id="5a71a-133">Обычно ярлыки для установленных командных строк помещаются в папку **меню "Пуск"** для Visual Studio, например в C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="5a71a-133">Usually, the shortcuts for the command prompts you have installed will be placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span></span>    <span data-ttu-id="5a71a-134">Но если по какой-то причине поиск командной строки не дает ожидаемых результатов, попробуйте вручную найти ярлык на компьютере, чтобы использовать его.</span><span class="sxs-lookup"><span data-stu-id="5a71a-134">But if for some reason, searching for the command prompt doesn't yield the expected results, you can try to manually locate the shortcut on your machine in order to use it.</span></span>   <span data-ttu-id="5a71a-135">Попробуйте ввести имя файла командной строки, например VsDevCmd.bat, или перейдите в папку средств, например в C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (точный путь зависит от версии Visual Studio и расположения установки).</span><span class="sxs-lookup"><span data-stu-id="5a71a-135">Try searching for the name of the command prompt file such as VsDevCmd.bat or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (path will change according to your Visual Studio version and installation location).</span></span>  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="5a71a-136">Запуск командной строки из Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a71a-136">Running command prompt from inside Visual Studio</span></span>  
 <span data-ttu-id="5a71a-137">Для упрощения доступа можно включить командную строку разработчика для Visual Studio или другую командную строку в меню "Инструменты" в Visual Studio, добавив ее в список внешних инструментов.</span><span class="sxs-lookup"><span data-stu-id="5a71a-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="5a71a-138">Вот как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="5a71a-138">This is how you can accomplish that:</span></span>  
  
1.  <span data-ttu-id="5a71a-139">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5a71a-139">Open Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5a71a-140">Выберите меню **Инструменты** и выберите в нем пункт **Внешние инструменты...**</span><span class="sxs-lookup"><span data-stu-id="5a71a-140">Select the **Tools** menu and choose **External Tools...**.</span></span>  
  
3.  <span data-ttu-id="5a71a-141">В диалоговом окне **Внешние инструменты** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5a71a-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="5a71a-142">Появится новый элемент.</span><span class="sxs-lookup"><span data-stu-id="5a71a-142">A new entry appears</span></span>  
  
4.  <span data-ttu-id="5a71a-143">Введите **заголовок** для нового пункта меню, например `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>  
  
5.  <span data-ttu-id="5a71a-144">В поле **Команда** укажите файл, который должен запускаться, например `%comspec%` или `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="5a71a-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe` .</span></span>  
  
6.  <span data-ttu-id="5a71a-145">В поле **Аргументы** укажите, где найти конкретную командную строку, которую вы хотите использовать, например `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (это будет запускать командную строку разработчика, установленную с [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5a71a-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (this will launch the Developer Command Prompt installed with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span></span> <span data-ttu-id="5a71a-146">Это значение следует изменить в соответствии с вашей версией Visual Studio и расположением установки.</span><span class="sxs-lookup"><span data-stu-id="5a71a-146">This value needs to be changed according to your Visual Studio version and installation location.</span></span>  
  
7.  <span data-ttu-id="5a71a-147">Выберите значение для поля **Исходный каталог**, например **Каталог проекта**.</span><span class="sxs-lookup"><span data-stu-id="5a71a-147">Choose a value for the **Initial directory** field such as **Project Directory** .</span></span>  
  
8.  <span data-ttu-id="5a71a-148">Нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="5a71a-148">Choose the **OK** button.</span></span>  
  
 <span data-ttu-id="5a71a-149">После этого новый элемент добавляется в меню, и вы можете вызывать командную строку из меню **Инструменты**.</span><span class="sxs-lookup"><span data-stu-id="5a71a-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a71a-150">См. также</span><span class="sxs-lookup"><span data-stu-id="5a71a-150">See Also</span></span>  
 <span data-ttu-id="5a71a-151">[Инструменты](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a71a-151">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 [<span data-ttu-id="5a71a-152">Управление внешними инструментами</span><span class="sxs-lookup"><span data-stu-id="5a71a-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)

