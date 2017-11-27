---
title: "Примеры командных строк компиляции (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)
В качестве альтернативы для компиляции [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы изнутри [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], можно скомпилировать из командной строки для создания исполняемых файлов (.exe) или файлы библиотеки динамической компоновки (DLL).  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор командной строки поддерживает полный набор параметров, входные и выходные файлы, сборки и отладки элементов управления и параметров препроцессора. Каждый параметр доступен в двух формах: `-``option` и `/``option`. В данном документе показана только `/``option` формы.  
  
 В следующей таблице перечислены некоторые примеры команд командной строки, которые можно изменять для собственного использования.  
  
|Целевой тип|Применение|  
|--------|---------|  
|Скомпилируйте файл VB и создайте File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Скомпилируйте файл VB и создайте File.dll|`vbc /target:library File.vb`|  
|Скомпилируйте файл VB и создайте My.exe|`vbc /out:My.exe File.vb`|  
|Скомпилируйте все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге с оптимизацией и `DEBUG` символ определен, формирующего File2.exe|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Скомпилируйте все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Скомпилируйте все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге в Something.dll|`vbc /target:library /out:Something.dll *.vb`|  
  
 При компиляции из командной строки, необходимо явно ссылаться Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] библиотеку времени выполнения с помощью `/reference` параметр компилятора.  
  
> [!TIP]
>  При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода. Чтобы отобразить эти сведения, откройте [диалоговое окно «Параметры», проекты и решения, построения и выполнения](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **детализации, выходные данные построения проекта MSBuild** для **обычный** или более высоком уровне детализации. Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
