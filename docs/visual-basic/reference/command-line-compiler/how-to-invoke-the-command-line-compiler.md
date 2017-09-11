---
title: "Практическое руководство: вызов компилятора командной строки (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e19bb506b016b774d2c497f8b17d91b35afb3eef
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="a31d2-102">Практическое руководство. Вызов компилятора командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a31d2-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="a31d2-103">Можно вызвать компилятор командной строки, введя имя исполняемого файла в командной строке, также называется командной строки MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="a31d2-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="a31d2-104">Если компиляция выполняется из командной строки Windows, необходимо ввести полный путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="a31d2-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="a31d2-105">Чтобы переопределить это поведение по умолчанию, можно использовать либо [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] командной строки или изменить переменную среды PATH.</span><span class="sxs-lookup"><span data-stu-id="a31d2-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="a31d2-106">Оба позволяют выполнять компиляцию из любого каталога, просто указывая имя компилятора.</span><span class="sxs-lookup"><span data-stu-id="a31d2-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="a31d2-107">Для вызова компилятора с помощью командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a31d2-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="a31d2-108">Откройте папку средств Visual Studio программы в группе программ Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a31d2-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="a31d2-109">Можно использовать [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] командной строки для доступа к компилятору из любого каталога на компьютере, если установлена среда Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a31d2-109">You can use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="a31d2-110">Вызов [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] командной строки.</span><span class="sxs-lookup"><span data-stu-id="a31d2-110">Invoke the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="a31d2-111">В командной строке введите `vbc.exe` *Имя_файла_исходного_кода* и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a31d2-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="a31d2-112">Например, если исходный код сохранен в каталоге с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` , чтобы перейти в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="a31d2-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="a31d2-113">Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="a31d2-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="a31d2-114">Для установки переменной среды PATH для компилятора командной строки для Windows</span><span class="sxs-lookup"><span data-stu-id="a31d2-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="a31d2-115">Используйте функцию поиска Windows, чтобы найти Vbc.exe на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="a31d2-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="a31d2-116">Точное имя каталога, в котором расположен компилятор, зависит от расположения каталога Windows и версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] установлен.</span><span class="sxs-lookup"><span data-stu-id="a31d2-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed.</span></span> <span data-ttu-id="a31d2-117">При наличии более чем одной версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] установлен, вам необходимо определить, какую версию следует использовать (как правило, это последняя версия).</span><span class="sxs-lookup"><span data-stu-id="a31d2-117">If you have more than one version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="a31d2-118">Из вашего **запустить** меню, щелкните правой кнопкой мыши **Мой компьютер**и нажмите кнопку **свойства** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="a31d2-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="a31d2-119">Щелкните **Дополнительно** , а затем щелкните **переменных среды**.</span><span class="sxs-lookup"><span data-stu-id="a31d2-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="a31d2-120">В **системы** панель «переменные», выберите **путь** из списка и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a31d2-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="a31d2-121">В **Изменение системной** переменных диалоговое окно, переместите курсор в конец строки в **значение переменной** и введите точку с запятой (;) следуют полное имя каталога на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="a31d2-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="a31d2-122">Щелкните **ОК** чтобы подтвердить изменения и закрыть диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="a31d2-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="a31d2-123">После изменения переменной среды PATH можно запустить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятора в командной строке Windows из любого каталога на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a31d2-123">After you change the PATH environment variable, you can run the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="a31d2-124">Вызов компилятора командной строки Windows</span><span class="sxs-lookup"><span data-stu-id="a31d2-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="a31d2-125">От **запустить** выберите пункт **стандартные** папку, а затем откройте **командной строки Windows**.</span><span class="sxs-lookup"><span data-stu-id="a31d2-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="a31d2-126">В командной строке введите `vbc.exe` *Имя_файла_исходного_кода* и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a31d2-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="a31d2-127">Например, если исходный код сохранен в каталоге с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` , чтобы перейти в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="a31d2-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="a31d2-128">Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="a31d2-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31d2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a31d2-129">See Also</span></span>  
 <span data-ttu-id="a31d2-130">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a31d2-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a31d2-131"> [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="a31d2-131"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
