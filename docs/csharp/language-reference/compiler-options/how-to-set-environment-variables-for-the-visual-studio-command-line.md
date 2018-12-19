---
title: Как выполнить Настройка переменных среды для командной строки Visual Studio
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
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
ms.openlocfilehash: 3563f668dfd4610e1c5cd7d7f8633943c654f193
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286446"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="4ca81-102">Как выполнить Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4ca81-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="4ca81-103">Файл VsDevCmd.bat задает переменные среды для поддержки построения из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4ca81-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="4ca81-104">В состав Visual Studio 2017 включен новый файл VsDevCmd.bat.</span><span class="sxs-lookup"><span data-stu-id="4ca81-104">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="4ca81-105">В Visual Studio 2015 и более ранних версий для этих целей использовался файл VSVARS32.bat.</span><span class="sxs-lookup"><span data-stu-id="4ca81-105">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="4ca81-106">Этот файл располагался в каталоге \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools или Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="4ca81-106">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="4ca81-107">Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл VsDevCmd.bat или VSVARS32.BAT из других версий в том же окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="4ca81-107">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="4ca81-108">Вместо этого необходимо выполнять команду для каждой версии в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="4ca81-108">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="4ca81-109">Выполнение файла VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="4ca81-109">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="4ca81-110">В меню **Пуск** выберите пункт **Командная строка разработчика для VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-110">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="4ca81-111">Он находится в папке **Visual Studio 2017**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-111">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="4ca81-112">Перейдите в подкаталог \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools или \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools в зависимости от вашей установки.</span><span class="sxs-lookup"><span data-stu-id="4ca81-112">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="4ca81-113">(Текущая версия: *Версия* — *2017*.</span><span class="sxs-lookup"><span data-stu-id="4ca81-113">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="4ca81-114">*Предложение* — *Enterprise*, *Professional* или *Community*.)</span><span class="sxs-lookup"><span data-stu-id="4ca81-114">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="4ca81-115">Чтобы выполнить файл VsDevCmd.bat, введите **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="4ca81-115">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="4ca81-116">Файл VsDevCmd.bat может иметь отличия на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4ca81-116">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="4ca81-117">Не заменяйте отсутствующий или поврежденный файл VsDevCmd.bat файлом VsDevCmd.bat с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="4ca81-117">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="4ca81-118">Вместо этого повторите установку, чтобы заменить отсутствующий файл.</span><span class="sxs-lookup"><span data-stu-id="4ca81-118">Instead, rerun setup to replace the missing file.</span></span>  

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="4ca81-119">Доступные параметры для VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="4ca81-119">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="4ca81-120">Чтобы просмотреть доступные параметры для VsDevCmd.BAT, выполните команду с параметром `-help`:</span><span class="sxs-lookup"><span data-stu-id="4ca81-120">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>
```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="4ca81-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca81-121">See Also</span></span>  

- [<span data-ttu-id="4ca81-122">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="4ca81-122">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
