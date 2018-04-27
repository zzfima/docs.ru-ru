---
title: Примеры командных строк компиляции (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b61ef6facf33fa043cad28a78405a19308a9864f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)
В качестве альтернативы для компиляции Visual Basic в Visual Studio можно компилировать из командной строки для создания исполняемых файлов (.exe) или файлы библиотеки динамической компоновки (DLL).  
  
 Компилятор командной строки Visual Basic поддерживает полный набор параметров для управления входными и выходные файлы, сборки, отладки и параметры препроцессора. Каждый параметр доступен в двух формах: `-option` и `/option`. В данном документе показана только `-option` формы.  
  
 В следующей таблице перечислены некоторые примеры команд командной строки, которые можно изменять для собственного использования.  
  
|Кому|Использовать|  
|--------|---------|  
|Скомпилируйте файл VB и создайте File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Скомпилируйте файл VB и создайте File.dll|`vbc -target:library File.vb`|  
|Скомпилируйте файл VB и создайте My.exe|`vbc -out:My.exe File.vb`|  
|Скомпилируйте файл VB и создание библиотеки и ссылочную сборку с именем File.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Компилировать все файлы Visual Basic в текущем каталоге с оптимизацией на и `DEBUG` символ определен, формирующего File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Компилировать все файлы Visual Basic в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Компилировать все файлы Visual Basic в текущем каталоге в Something.dll|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода. Чтобы отобразить эти сведения, откройте [диалоговое окно «Параметры», проекты и решения, построения и выполнения](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **детализации, выходные данные построения проекта MSBuild** для **обычный** или более высоком уровне детализации.   
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
