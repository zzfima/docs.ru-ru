---
title: Практическое руководство. Вызов компилятора командной строки
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344260"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="4641c-102">Практическое руководство. Вызов компилятора командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4641c-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>

<span data-ttu-id="4641c-103">Можно вызвать компилятор командной строки, введя имя исполняемого файла в командную строку, которая также называется командной строкой MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="4641c-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="4641c-104">При компиляции из командной строки Windows по умолчанию необходимо ввести полный путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="4641c-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="4641c-105">Чтобы переопределить это поведение по умолчанию, можно либо использовать Командная строка разработчика для Visual Studio, либо изменить переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="4641c-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="4641c-106">Оба варианта позволяют компилировать из любого каталога, просто вводя имя компилятора.</span><span class="sxs-lookup"><span data-stu-id="4641c-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="4641c-107">Вызов компилятора с помощью Командная строка разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4641c-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>

1. <span data-ttu-id="4641c-108">Откройте папку Инструменты Visual Studio Program в Microsoft Visual Studio группе программ.</span><span class="sxs-lookup"><span data-stu-id="4641c-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>

2. <span data-ttu-id="4641c-109">Вы можете использовать Командная строка разработчика для Visual Studio, чтобы получить доступ к компилятору из любого каталога на компьютере, если установлен Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4641c-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>

3. <span data-ttu-id="4641c-110">Вызов Командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4641c-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>

4. <span data-ttu-id="4641c-111">В командной строке введите `vbc.exe` *саурцефиленаме* и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="4641c-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>

    <span data-ttu-id="4641c-112">Например, если вы сохранили исходный код в каталоге с именем `SourceFiles`, откройте командную строку и введите `cd SourceFiles`, чтобы перейти к этому каталогу.</span><span class="sxs-lookup"><span data-stu-id="4641c-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="4641c-113">Если каталог содержит исходный файл с именем `Source.vb`, его можно скомпилировать, введя `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="4641c-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="4641c-114">Задание переменной среды PATH компилятору для командной строки Windows</span><span class="sxs-lookup"><span data-stu-id="4641c-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>

1. <span data-ttu-id="4641c-115">С помощью функции поиска Windows найдите файл Vbc. exe на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="4641c-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>

    <span data-ttu-id="4641c-116">Точное имя каталога, в котором находится компилятор, зависит от расположения каталога Windows и версии установленного ".NET Framework".</span><span class="sxs-lookup"><span data-stu-id="4641c-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="4641c-117">Если установлена более одна версия ".NET Framework", необходимо определить, какую версию следует использовать (как правило, это последняя версия).</span><span class="sxs-lookup"><span data-stu-id="4641c-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>

2. <span data-ttu-id="4641c-118">В меню " **Пуск** " щелкните правой кнопкой мыши **Мой компьютер**, а затем в контекстном меню выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="4641c-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>

3. <span data-ttu-id="4641c-119">Откройте вкладку **Дополнительно**, затем нажмите кнопку **Переменные среды**.</span><span class="sxs-lookup"><span data-stu-id="4641c-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>

4. <span data-ttu-id="4641c-120">В области **системные** переменные выберите **путь** из списка и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="4641c-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>

5. <span data-ttu-id="4641c-121">В диалоговом окне **Изменение системной** переменной переместите курсор в конец строки в поле **значение переменной** и введите точку с запятой (;) , за которым следует полное имя каталога, найденное на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4641c-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>

6. <span data-ttu-id="4641c-122">Нажмите кнопку **ОК** , чтобы подтвердить изменения и закрыть диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="4641c-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>

     <span data-ttu-id="4641c-123">После изменения переменной среды PATH можно запустить компилятор Visual Basic в командной строке Windows из любого каталога на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4641c-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="4641c-124">Вызов компилятора с помощью командной строки Windows</span><span class="sxs-lookup"><span data-stu-id="4641c-124">To invoke the compiler using the Windows Command Prompt</span></span>

1. <span data-ttu-id="4641c-125">В меню **Пуск** выберите папку **стандартные** , а затем откройте **командную строку Windows**.</span><span class="sxs-lookup"><span data-stu-id="4641c-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>

2. <span data-ttu-id="4641c-126">В командной строке введите `vbc.exe`*саурцефиленаме* и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="4641c-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>

     <span data-ttu-id="4641c-127">Например, если вы сохранили исходный код в каталоге с именем `SourceFiles`, откройте командную строку и введите `cd SourceFiles`, чтобы перейти к этому каталогу.</span><span class="sxs-lookup"><span data-stu-id="4641c-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="4641c-128">Если каталог содержит исходный файл с именем `Source.vb`, его можно скомпилировать, введя `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="4641c-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4641c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4641c-129">See also</span></span>

- [<span data-ttu-id="4641c-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="4641c-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4641c-131">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="4641c-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
