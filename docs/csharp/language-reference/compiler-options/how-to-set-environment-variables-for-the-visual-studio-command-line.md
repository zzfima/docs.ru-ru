---
title: "Практическое руководство. Настройка переменных среды для командной строки Visual Studio"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
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
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 569683169c6d7ae50c33ed06d3b365a663f16715
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="e769b-102">Практическое руководство. Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e769b-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>
<span data-ttu-id="e769b-103">Файл vsvars32.bat задает переменные среды для поддержки построения из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e769b-103">The vsvars32.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="e769b-104">Дополнительные сведения о файле vsvars32.bat см. в [статье базы знаний Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="e769b-104">For more information about vsvars32.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  
  
 <span data-ttu-id="e769b-105">Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл vsvars32.bat или vcvars32.bat из других версий в том же окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="e769b-105">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run vsvars32.bat or vcvars32.bat from different versions in the same Command Prompt window.</span></span>  
  
### <a name="to-run-vsvars32bat"></a><span data-ttu-id="e769b-106">Запуск VSVARS32.BAT</span><span class="sxs-lookup"><span data-stu-id="e769b-106">To run VSVARS32.BAT</span></span>  
  
1.  <span data-ttu-id="e769b-107">В меню **Пуск** выберите пункт **Командная строка разработчика для VS2012**.</span><span class="sxs-lookup"><span data-stu-id="e769b-107">From the **Start** menu, open the **Developer Command Prompt for VS2012**.</span></span>  
  
2.  <span data-ttu-id="e769b-108">Перейдите в подкаталог Program Files\Microsoft Visual Studio *версия*\Common7\Tools или Program Files (x86)\Microsoft Visual Studio *версия*\Common7\Tools в зависимости от вашей установки.</span><span class="sxs-lookup"><span data-stu-id="e769b-108">Change to the Program Files\Microsoft Visual Studio *Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools subdirectory of your installation.</span></span>  
  
3.  <span data-ttu-id="e769b-109">Введите **VSVARS32**, чтобы запустить файл VSVARS32.bat.</span><span class="sxs-lookup"><span data-stu-id="e769b-109">Run VSVARS32.bat by typing **VSVARS32**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e769b-110">Файл VSVARS32.bat может иметь отличия на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="e769b-110">VSVARS32.bat can vary from computer to computer.</span></span> <span data-ttu-id="e769b-111">Не заменяйте отсутствующий или поврежденный файл VSVARS32.bat файлом VSVARS32.bat с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="e769b-111">Do not replace a missing or damaged VSVARS32.bat file with a VSVARS32.bat from another computer.</span></span> <span data-ttu-id="e769b-112">Вместо этого повторите установку, чтобы заменить отсутствующий файл.</span><span class="sxs-lookup"><span data-stu-id="e769b-112">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e769b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e769b-113">See Also</span></span>  
 [<span data-ttu-id="e769b-114">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="e769b-114">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

