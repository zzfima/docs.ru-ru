---
title: Настройка переменных среды для командной строки Visual Studio
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
ms.openlocfilehash: 3b69a92d28663bbbd34245435a69aea80d20fdc9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972830"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Настройка переменных среды для командной строки Visual Studio

Файл VsDevCmd.bat задает переменные среды для поддержки построения из командной строки.

> [!NOTE]
> В состав Visual Studio 2017 включен новый файл VsDevCmd.bat. В Visual Studio 2015 и более ранних версий для этих целей использовался файл VSVARS32.bat. Этот файл располагался в каталоге \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools или Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.

Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл VsDevCmd.bat или VSVARS32.BAT из других версий в том же окне командной строки. Вместо этого необходимо выполнять команду для каждой версии в отдельном окне.

### <a name="to-run-vsdevcmdbat"></a>Выполнение файла VsDevCmd.BAT

1. В меню **Пуск** выберите пункт **Командная строка разработчика для VS 2017**.  Он находится в папке **Visual Studio 2017**.

2. Перейдите в подкаталог \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools или \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools в зависимости от вашей установки.  (Текущая версия: *Версия* — *2017*. *Предложение* — *Enterprise*, *Professional* или *Community*.)

3. Чтобы выполнить файл VsDevCmd.bat, введите **VsDevCmd**.

    > [!CAUTION]
    > Файл VsDevCmd.bat может иметь отличия на разных компьютерах. Не заменяйте отсутствующий или поврежденный файл VsDevCmd.bat файлом VsDevCmd.bat с другого компьютера. Вместо этого повторите установку, чтобы заменить отсутствующий файл.

### <a name="available-options-for-vsdevcmdbat"></a>Доступные параметры для VsDevCmd.BAT

Чтобы просмотреть доступные параметры для VsDevCmd.BAT, выполните команду с параметром `-help`:

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a>См. также

- [Сборка из командной строки с помощью csc.exe](./command-line-building-with-csc-exe.md)
