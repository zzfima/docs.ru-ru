---
title: Настройка переменных среды для командной строки Visual Studio
ms.date: 12/20/2019
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
ms.openlocfilehash: 99e2a837877494dd4c7e0106047bce3cc39a9282
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342369"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="229cf-102">Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="229cf-102">How to set environment variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="229cf-103">Файл VsDevCmd.bat задает переменные среды для поддержки построения из командной строки.</span><span class="sxs-lookup"><span data-stu-id="229cf-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="229cf-104">В Visual Studio 2015 и ниже для этих целей использовался файл VSVARS32.bat (не VsDevCmd.bat).</span><span class="sxs-lookup"><span data-stu-id="229cf-104">Visual Studio 2015 and earlier versions used VSVARS32.bat, not VsDevCmd.bat for the same purpose.</span></span> <span data-ttu-id="229cf-105">Этот файл располагался в каталоге \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools или Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="229cf-105">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="229cf-106">Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл VsDevCmd.bat или VSVARS32.BAT из других версий в том же окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="229cf-106">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="229cf-107">Вместо этого необходимо выполнять команду для каждой версии в отдельном окне.</span><span class="sxs-lookup"><span data-stu-id="229cf-107">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="229cf-108">Выполнение файла VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="229cf-108">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="229cf-109">В меню **Пуск** выберите пункт **Командная строка разработчика для VS 2019**.</span><span class="sxs-lookup"><span data-stu-id="229cf-109">From the **Start** menu, open the **Developer Command Prompt for VS 2019**.</span></span>  <span data-ttu-id="229cf-110">Он находится в папке **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="229cf-110">It's in the **Visual Studio 2019** folder.</span></span>

2. <span data-ttu-id="229cf-111">Перейдите в подкаталог \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools или \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools в зависимости от вашей установки.</span><span class="sxs-lookup"><span data-stu-id="229cf-111">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="229cf-112">(*Текущая версия* — *2019*.</span><span class="sxs-lookup"><span data-stu-id="229cf-112">(*Version* is *2019* for the current version.</span></span> <span data-ttu-id="229cf-113">*Предложение* — *Enterprise*, *Professional* или *Community*.)</span><span class="sxs-lookup"><span data-stu-id="229cf-113">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="229cf-114">Чтобы выполнить файл VsDevCmd.bat, введите **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="229cf-114">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="229cf-115">Файл VsDevCmd.bat может иметь отличия на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="229cf-115">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="229cf-116">Не заменяйте отсутствующий или поврежденный файл VsDevCmd.bat файлом VsDevCmd.bat с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="229cf-116">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="229cf-117">Вместо этого повторите установку, чтобы заменить отсутствующий файл.</span><span class="sxs-lookup"><span data-stu-id="229cf-117">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="229cf-118">Доступные параметры для VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="229cf-118">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="229cf-119">Чтобы просмотреть доступные параметры для VsDevCmd.BAT, выполните команду с параметром `-help`:</span><span class="sxs-lookup"><span data-stu-id="229cf-119">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="229cf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="229cf-120">See also</span></span>

- [<span data-ttu-id="229cf-121">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="229cf-121">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
