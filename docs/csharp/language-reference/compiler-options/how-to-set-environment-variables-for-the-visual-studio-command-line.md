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
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Практическое руководство. Настройка переменных среды для командной строки Visual Studio

Файл VsDevCmd.bat устанавливает соответствующие переменные среды для включения сборки из командной строки. Дополнительные сведения о VsDevCmd.bat см. в разделе [статье базы знаний Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  

> [!NOTE]
> Файл VsDevCmd.bat является новый файл в комплекте с Visual Studio 2017 г. Visual Studio 2015 и более ранних версий использовать файл VSVARS32.bat для той же цели. Этот файл был сохранен в Visual Studio \Program Files\Microsoft\\*версии*\Common7\Tools или Program Files (x86) \Microsoft Visual Studio\\*версии*\Common7\Tools.
  
Если текущая версия Visual Studio установлена на компьютере с более ранней версии Visual Studio, не следует запускать VsDevCmd.bat и VSVARS32. BAT из разных версий в том же окне командной строки. Вместо этого необходимо выполнить команду для каждой версии в отдельном окне.
  
### <a name="to-run-vsdevcmdbat"></a>Для запуска VsDevCmd.BAT  
  
1.  Из **запустить** выберите пункт **Командная строка разработчика для VS 2017 г**.  Он находится в **2017 г. Visual Studio** папки.
  
2.  Изменения в \Program Files\Microsoft Visual Studio\\*версии*\\*предложения*\Common7\Tools или \Program файлы (x86) \Microsoft Visual Studio\\ *Версии*\\*предложения*\Common7\Tools установочного каталога.  (*Версии* — *2017 г* для текущей версии. *Предложения* является одним из *Enterprise*, *Professional* или *сообщества*.)
  
3.  Для запуска VsDevCmd.bat введите **VsDevCmd**.  
  
    > [!CAUTION]
    >  VsDevCmd.bat могут различаться на разных компьютерах. Не заменяйте отсутствующий или поврежденный файл VsDevCmd.bat с VsDevCmd.bat с другого компьютера. Вместо этого повторите установку, чтобы заменить отсутствующий файл.  
  
## <a name="see-also"></a>См. также  
 [Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
