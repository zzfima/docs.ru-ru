---
title: Примеры командных строк компиляции (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 0771ed41d6c58ce7cc98435b405f5819e45393db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916764"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)
В качестве альтернативы компиляции программ Visual Basic из среды Visual Studio можно скомпилировать из командной строки для создания исполняемых файлов (.exe) или файлы библиотеки динамической компоновки (DLL).  
  
 Компилятор командной строки Visual Basic поддерживает полный набор параметров, которые управляют входные и выходные файлы, сборки и отладки и параметры препроцессора. Каждый параметр доступен в двух формах: `-option` и `/option`. В этой документации показаны только `-option` формы.  
  
 В следующей таблице перечислены некоторые примеры команд командной строки, которые можно изменять в собственных целях.  
  
|Кому|Использовать|  
|--------|---------|  
|Скомпилируйте файл VB как и создание File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Скомпилируйте файл VB как и создание File.dll|`vbc -target:library File.vb`|  
|Скомпилируйте файл VB как и создание My.exe|`vbc -out:My.exe File.vb`|  
|Скомпилируйте файл VB как и создает библиотеку и ссылочную сборку с именем File.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Компиляция всех файлов Visual Basic в текущем каталоге с оптимизацией на и `DEBUG` символ определен, создания File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Компиляция всех файлов Visual Basic в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Компиляция всех файлов Visual Basic в текущем каталоге в Something.dll|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода. Чтобы отобразить эту информацию, откройте [диалоговое окно "Параметры", проекты и решения, построения и выполнения](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **степень подробности сообщений при сборке проекта MSBuild** для **обычный** или более высокий уровень детализации.   
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
