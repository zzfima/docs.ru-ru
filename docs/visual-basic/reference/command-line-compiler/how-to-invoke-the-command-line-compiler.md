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
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 69c95289f91f712bd3fda03a7f582d879141591a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Практическое руководство. Вызов компилятора командной строки (Visual Basic)
Можно вызвать компилятор командной строки, введя имя исполняемого файла в командной строке, также называется командной строки MS-DOS. Если компиляция выполняется из командной строки Windows, необходимо ввести полный путь к исполняемому файлу. Чтобы переопределить это поведение по умолчанию, можно использовать либо [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] командной строки или изменить переменную среды PATH. Оба позволяют выполнять компиляцию из любого каталога, просто указывая имя компилятора.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Для вызова компилятора с помощью командной строки Visual Studio  
  
1.  Откройте папку средств Visual Studio программы в группе программ Microsoft Visual Studio.  
  
2.  Можно использовать [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] командной строки для доступа к компилятору из любого каталога на компьютере, если установлена среда Visual Studio.  
  
3.  Вызов [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] командной строки.  
  
4.  В командной строке введите `vbc.exe` *Имя_файла_исходного_кода* и нажмите клавишу ВВОД.  
  
     Например, если исходный код сохранен в каталоге с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` , чтобы перейти в этот каталог. Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Для установки переменной среды PATH для компилятора командной строки для Windows  
  
1.  Используйте функцию поиска Windows, чтобы найти Vbc.exe на локальном диске.  
  
     Точное имя каталога, в котором расположен компилятор, зависит от расположения каталога Windows и версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] установлен. При наличии более чем одной версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] установлен, вам необходимо определить, какую версию следует использовать (как правило, это последняя версия).  
  
2.  Из вашего **запустить** меню, щелкните правой кнопкой мыши **Мой компьютер**и нажмите кнопку **свойства** в контекстном меню.  
  
3.  Щелкните **Дополнительно** , а затем щелкните **переменных среды**.  
  
4.  В **системы** панель «переменные», выберите **путь** из списка и нажмите кнопку **изменить**.  
  
5.  В **Изменение системной** переменных диалоговое окно, переместите курсор в конец строки в **значение переменной** и введите точку с запятой (;) следуют полное имя каталога на шаге 1.  
  
6.  Щелкните **ОК** чтобы подтвердить изменения и закрыть диалоговые окна.  
  
     После изменения переменной среды PATH можно запустить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятора в командной строке Windows из любого каталога на компьютере.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Вызов компилятора командной строки Windows  
  
1.  От **запустить** выберите пункт **стандартные** папку, а затем откройте **командной строки Windows**.  
  
2.  В командной строке введите `vbc.exe` *Имя_файла_исходного_кода* и нажмите клавишу ВВОД.  
  
     Например, если исходный код сохранен в каталоге с именем `SourceFiles`, нужно будет открыть командную строку и введите `cd SourceFiles` , чтобы перейти в этот каталог. Если каталог, содержащий исходный файл с именем `Source.vb`, скомпилировать его, введя `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
