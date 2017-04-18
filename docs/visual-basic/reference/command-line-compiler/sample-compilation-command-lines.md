---
title: "Примеры командных строк компиляции (Visual Basic) | Документы Microsoft"
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
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 918787b3377f2e5a636a6b098046ac2f455efcdd
ms.lasthandoff: 03/13/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)
В качестве альтернативы для компиляции [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы изнутри [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], можно компилировать из командной строки для создания исполняемых файлов (.exe) или файлов библиотеки динамической компоновки (.dll).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятора командной строки поддерживает полный набор параметров, определяющих входных и выходных файлов, сборки и отладки и параметров препроцессора. Каждый параметр доступен в двух формах: `-``option` и `/``option`. В данном документе показана только `/``option` формы.  
  
 В следующей таблице перечислены некоторые примеры командных строк, которые можно изменять для собственного использования.  
  
|Целевой тип|Применение|  
|--------|---------|  
|Компиляция File.vb и создать File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Компиляция File.vb и создание файла File.dll|`vbc /target:library File.vb`|  
|Компиляция File.vb и создать My.exe|`vbc /out:My.exe File.vb`|  
|Скомпилируйте все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге с оптимизацией на и `DEBUG` символ определен, создавая File2.exe|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Скомпилируйте все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Скомпилируйте все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге в Something.dll|`vbc /target:library /out:Something.dll *.vb`|  
  
 При компиляции из командной строки, необходимо явно ссылаться Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] библиотеки времени выполнения с помощью `/reference` параметр компилятора.  
  
> [!TIP]
>  При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода. Для отображения этих сведений откройте [диалоговое окно «Параметры», проектов и решений, построения и выполнения](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **уровень детализации выходных данных построения проекта MSBuild** для **норм** или более высокий уровень детализации. Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
