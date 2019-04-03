---
title: Практическое руководство. Вызов компилятора командной строки (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 78bf5b1f19db3a4f39e263cfd71283f0f7718631
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817192"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="287ba-102">Практическое руководство. Вызов компилятора командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="287ba-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="287ba-103">Можно вызвать компилятор командной строки, введя имя соответствующего исполняемого файла в командной строке, также называется командной строки MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="287ba-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="287ba-104">При компиляции из командной строки Windows по умолчанию, необходимо ввести полный путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="287ba-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="287ba-105">Чтобы переопределить это поведение по умолчанию, можно использовать командную строку разработчика для Visual Studio, или изменить переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="287ba-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="287ba-106">Оба позволяют компилировать из любого каталога, просто введя его имя.</span><span class="sxs-lookup"><span data-stu-id="287ba-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="287ba-107">Для вызова компилятора, с помощью командной строки разработчика для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="287ba-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>  
  
1.  <span data-ttu-id="287ba-108">Откройте папку средств Visual Studio программы в группе программ Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="287ba-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="287ba-109">Командная строка разработчика для Visual Studio можно использовать для доступа к компилятору из любого каталога на компьютере, если установлена среда Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="287ba-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="287ba-110">Вызовите командную строку разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="287ba-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>  
  
4.  <span data-ttu-id="287ba-111">В командной строке введите `vbc.exe` *sourceFileName* и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="287ba-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="287ba-112">Например, если вы сохранили исходный код в каталог с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` для изменения в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="287ba-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="287ba-113">Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="287ba-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="287ba-114">Для задания переменной среды PATH для компилятора командной строки для Windows</span><span class="sxs-lookup"><span data-stu-id="287ba-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="287ba-115">Используйте функцию Windows Search для поиска Vbc.exe на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="287ba-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="287ba-116">Точное имя каталога, где находится компилятор зависит от расположения каталога Windows и версии «Установлена платформа .NET Framework».</span><span class="sxs-lookup"><span data-stu-id="287ba-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="287ba-117">При наличии более чем одну версию «Установлена платформа .NET Framework», необходимо определить, какую версию следует использовать (как правило, это последняя версия).</span><span class="sxs-lookup"><span data-stu-id="287ba-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="287ba-118">Из вашей **запустить** меню, щелкните правой кнопкой мыши **Мой компьютер**, а затем нажмите кнопку **свойства** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="287ba-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="287ba-119">Нажмите кнопку **Дополнительно** , а затем щелкните **переменные среды**.</span><span class="sxs-lookup"><span data-stu-id="287ba-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="287ba-120">В **системы** панель «переменные», выберите **путь** в списке и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="287ba-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="287ba-121">В **Изменение системной** переменной диалоговом окне переместить курсор в конец строки в **значение переменной** поле и введите точку с запятой (;) следуют полное имя каталога на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="287ba-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="287ba-122">Нажмите кнопку **ОК** чтобы подтвердить изменения и закройте диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="287ba-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="287ba-123">После изменения переменной среды PATH, запуском компилятор Visual Basic в командной строке Windows из любого каталога на компьютере.</span><span class="sxs-lookup"><span data-stu-id="287ba-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="287ba-124">Для вызова компилятора, с помощью командной строки Windows</span><span class="sxs-lookup"><span data-stu-id="287ba-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="287ba-125">Из **запустить** меню, щелкните **стандартные** папку, а затем откройте **командной строки Windows**.</span><span class="sxs-lookup"><span data-stu-id="287ba-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="287ba-126">В командной строке введите `vbc.exe` *sourceFileName* и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="287ba-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="287ba-127">Например, если вы сохранили исходный код в каталог с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` для изменения в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="287ba-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="287ba-128">Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="287ba-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287ba-129">См. также</span><span class="sxs-lookup"><span data-stu-id="287ba-129">See also</span></span>

- [<span data-ttu-id="287ba-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="287ba-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="287ba-131">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="287ba-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
