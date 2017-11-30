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
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="402d1-102">Практическое руководство. Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="402d1-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="402d1-103">Файл VsDevCmd.bat устанавливает соответствующие переменные среды для включения сборки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="402d1-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="402d1-104">Дополнительные сведения о VsDevCmd.bat см. в разделе [статье базы знаний Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="402d1-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  

> [!NOTE]
> <span data-ttu-id="402d1-105">Файл VsDevCmd.bat является новый файл в комплекте с Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="402d1-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="402d1-106">Visual Studio 2015 и более ранних версий использовать файл VSVARS32.bat для той же цели.</span><span class="sxs-lookup"><span data-stu-id="402d1-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="402d1-107">Этот файл был сохранен в Visual Studio \Program Files\Microsoft\\*версии*\Common7\Tools или Program Files (x86) \Microsoft Visual Studio\\*версии*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="402d1-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="402d1-108">Если текущая версия Visual Studio установлена на компьютере с более ранней версии Visual Studio, не следует запускать VsDevCmd.bat и VSVARS32. BAT из разных версий в том же окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="402d1-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="402d1-109">Вместо этого необходимо выполнить команду для каждой версии в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="402d1-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="402d1-110">Для запуска VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="402d1-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="402d1-111">Из **запустить** выберите пункт **Командная строка разработчика для VS 2017 г**.</span><span class="sxs-lookup"><span data-stu-id="402d1-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="402d1-112">Он находится в **2017 г. Visual Studio** папки.</span><span class="sxs-lookup"><span data-stu-id="402d1-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="402d1-113">Изменения в \Program Files\Microsoft Visual Studio\\*версии*\\*предложения*\Common7\Tools или \Program файлы (x86) \Microsoft Visual Studio\\ *Версии*\\*предложения*\Common7\Tools установочного каталога.</span><span class="sxs-lookup"><span data-stu-id="402d1-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="402d1-114">(*Версии* — *2017 г* для текущей версии.</span><span class="sxs-lookup"><span data-stu-id="402d1-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="402d1-115">*Предложения* является одним из *Enterprise*, *Professional* или *сообщества*.)</span><span class="sxs-lookup"><span data-stu-id="402d1-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="402d1-116">Для запуска VsDevCmd.bat введите **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="402d1-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="402d1-117">VsDevCmd.bat могут различаться на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="402d1-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="402d1-118">Не заменяйте отсутствующий или поврежденный файл VsDevCmd.bat с VsDevCmd.bat с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="402d1-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="402d1-119">Вместо этого повторите установку, чтобы заменить отсутствующий файл.</span><span class="sxs-lookup"><span data-stu-id="402d1-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402d1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="402d1-120">See Also</span></span>  
 [<span data-ttu-id="402d1-121">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="402d1-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
