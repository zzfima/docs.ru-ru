---
title: Практическое руководство. Вызов компилятора командной строки (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Практическое руководство. Вызов компилятора командной строки (Visual Basic)
Можно вызвать компилятор командной строки, введя имя исполняемого файла в командной строке, также называется командной строки MS-DOS. Если компиляция выполняется из командной строки Windows, необходимо ввести полный путь к исполняемому файлу. Чтобы переопределить это поведение по умолчанию, можно использовать либо [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] командной строки или изменить переменную среды PATH. Оба позволяют компиляцию из любого каталога, просто введя его имя.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Чтобы вызвать компилятор с помощью командной строки Visual Studio  
  
1.  Откройте соответствующую ей папку средств Visual Studio в группе программ Microsoft Visual Studio.  
  
2.  Можно использовать [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] командной строки для доступа к компилятору из любого каталога на компьютере, если установлена среда Visual Studio.  
  
3.  Вызов [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] командной строки.  
  
4.  В командной строке введите `vbc.exe` *Имя_файла_исходного_кода* и нажмите клавишу ВВОД.  
  
     Например, если исходный код сохранен в каталоге с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` для изменения в этот каталог. Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Для задания переменной среды PATH для компилятора командной строки для Windows  
  
1.  Используйте функцию поиска Windows, чтобы найти Vbc.exe на локальном диске.  
  
     Точное имя каталога, в котором компилятор зависит от расположения каталога Windows и версии «Установлена платформа .NET Framework». Если имеется более одной версии «Установлена платформа .NET Framework», необходимо определить, какую версию следует использовать (обычно это последняя версия).  
  
2.  Из вашего **запустить** меню, щелкните правой кнопкой мыши **Мой компьютер**и нажмите кнопку **свойства** в контекстном меню.  
  
3.  Нажмите кнопку **Дополнительно** , а затем щелкните **переменных среды**.  
  
4.  В **системы** панель «переменные», выберите **путь** из списка и нажмите кнопку **изменить**.  
  
5.  В **Изменение системной** диалогового окна "переменной" Переместить курсор в конец строки в **значение переменной** и введите точку с запятой (;) следуют полное имя каталога в шаге 1.  
  
6.  Нажмите кнопку **ОК** чтобы подтвердить изменения и закрыть диалоговые окна.  
  
     После изменения переменной среды PATH, можно запустить компилятор Visual Basic в командной строке Windows из любого каталога на компьютере.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Вызов компилятора командной строки Windows  
  
1.  Из **запустить** меню, щелкните **стандартные** , а затем откройте **командной строки Windows**.  
  
2.  В командной строке введите `vbc.exe` *Имя_файла_исходного_кода* и нажмите клавишу ВВОД.  
  
     Например, если исходный код сохранен в каталоге с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` для изменения в этот каталог. Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
