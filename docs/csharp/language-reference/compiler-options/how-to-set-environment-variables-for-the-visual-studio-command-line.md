---
title: "Практическое руководство. Настройка переменных среды для командной строки Visual Studio"
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: afab503719f67cf7ad1762370ed3062e12ad88e9
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="37887-102">Практическое руководство. Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37887-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="37887-103">Файл VsDevCmd.bat задает переменные среды для поддержки построения из командной строки.</span><span class="sxs-lookup"><span data-stu-id="37887-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="37887-104">Дополнительные сведения о файле VsDevCmd.bat см. в [статье базы знаний Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span><span class="sxs-lookup"><span data-stu-id="37887-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span></span>  

> [!NOTE]
> <span data-ttu-id="37887-105">В состав Visual Studio 2017 включен новый файл VsDevCmd.bat.</span><span class="sxs-lookup"><span data-stu-id="37887-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="37887-106">В Visual Studio 2015 и более ранних версий для этих целей использовался файл VSVARS32.bat.</span><span class="sxs-lookup"><span data-stu-id="37887-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="37887-107">Этот файл располагался в каталоге \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools или Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="37887-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="37887-108">Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл VsDevCmd.bat или VSVARS32.BAT из других версий в том же окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="37887-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="37887-109">Вместо этого необходимо выполнять команду для каждой версии в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="37887-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="37887-110">Выполнение файла VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="37887-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="37887-111">В меню **Пуск** выберите пункт **Командная строка разработчика для VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="37887-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="37887-112">Он находится в папке **Visual Studio 2017**.</span><span class="sxs-lookup"><span data-stu-id="37887-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="37887-113">Перейдите в подкаталог \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools или \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools в зависимости от вашей установки.</span><span class="sxs-lookup"><span data-stu-id="37887-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="37887-114">(Текущая версия: *Версия* — *2017*.</span><span class="sxs-lookup"><span data-stu-id="37887-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="37887-115">*Предложение* — *Enterprise*, *Professional* или *Community*.)</span><span class="sxs-lookup"><span data-stu-id="37887-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="37887-116">Чтобы выполнить файл VsDevCmd.bat, введите **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="37887-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="37887-117">Файл VsDevCmd.bat может иметь отличия на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="37887-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="37887-118">Не заменяйте отсутствующий или поврежденный файл VsDevCmd.bat файлом VsDevCmd.bat с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="37887-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="37887-119">Вместо этого повторите установку, чтобы заменить отсутствующий файл.</span><span class="sxs-lookup"><span data-stu-id="37887-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37887-120">См. также</span><span class="sxs-lookup"><span data-stu-id="37887-120">See Also</span></span>  
 [<span data-ttu-id="37887-121">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="37887-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
