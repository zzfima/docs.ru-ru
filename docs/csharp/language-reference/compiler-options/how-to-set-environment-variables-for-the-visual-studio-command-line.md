---
title: "Практическое руководство. Настройка переменных среды для командной строки Visual Studio | Документация Майкрософт"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: e2cc644bb3b2c51615fe763224505b07e113ad62
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Практическое руководство. Настройка переменных среды для командной строки Visual Studio
Файл vsvars32.bat задает переменные среды для поддержки построения из командной строки. Дополнительные сведения о файле vsvars32.bat см. в [статье базы знаний Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  
  
 Если текущая версия Visual Studio установлена на компьютере, на котором также имеется более ранняя версия Visual Studio, не запускайте файл vsvars32.bat или vcvars32.bat из других версий в том же окне командной строки.  
  
### <a name="to-run-vsvars32bat"></a>Запуск VSVARS32.BAT  
  
1.  В меню **Пуск** выберите пункт **Командная строка разработчика для VS2012**.  
  
2.  Перейдите в подкаталог Program Files\Microsoft Visual Studio *версия*\Common7\Tools или Program Files (x86)\Microsoft Visual Studio *версия*\Common7\Tools в зависимости от вашей установки.  
  
3.  Введите **VSVARS32**, чтобы запустить файл VSVARS32.bat.  
  
    > [!CAUTION]
    >  Файл VSVARS32.bat может иметь отличия на разных компьютерах. Не заменяйте отсутствующий или поврежденный файл VSVARS32.bat файлом VSVARS32.bat с другого компьютера. Вместо этого повторите установку, чтобы заменить отсутствующий файл.  
  
## <a name="see-also"></a>См. также  
 [Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
