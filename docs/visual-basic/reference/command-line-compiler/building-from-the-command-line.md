---
title: "Построение из командной строки (Visual Basic) | Документы Microsoft"
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
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers, invoking from command line
- command-line builds
- compiling source code
- command-line compilers, Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
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
ms.openlocfilehash: 49f84c221e18457ab46534ca46da7c4764a8ee40
ms.lasthandoff: 03/13/2017

---
# <a name="building-from-the-command-line-visual-basic"></a>Построение из командной строки (Visual Basic)
A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проект состоит из одного или нескольких файлов отдельный источник. В процессе компиляции эти файлы соединяются в один пакет — исполняемый файл, который запускается как приложение.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет компилятор командной строки в качестве альтернативы для компиляции программы с [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] интегрированной среды разработки (IDE). Компилятор командной строки разработан для ситуаций, в которых не требуется полный набор функций в Интегрированной среде разработки, например, при использовании или создании программы на компьютере с ограниченными системными ресурсами или дисковым пространством.  
  
 При компиляции из командной строки, необходимо явно ссылаться Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] библиотеки времени выполнения с помощью `/reference` параметр компилятора.  
  
 Для компиляции исходных файлов из [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] интегрированной среды разработки, выберите **построения** из **построения** меню.  
  
> [!TIP]
>  При построении проекта файлы с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** команду и ее параметры в окне вывода. Для отображения этих сведений откройте [диалоговое окно «Параметры», проектов и решений, построения и выполнения](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **уровень детализации выходных данных построения проекта MSBuild** для **норм** или более высокий уровень детализации. Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 Файлы проекта (VBPROJ) в командной строке можно скомпилировать с помощью MSBuild. Дополнительные сведения см. в разделе [Справочник по командной строки](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) и [Пошаговое руководство: использование MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Вызов компилятора командной строки](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Описывается вызов компилятора командной строки, в командной строке MS-DOS или из определенной папки.  
  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Список примеров командных строк, которые можно изменять для собственного использования.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Предоставляет список параметров компилятора, упорядоченные по алфавиту или по назначению.  
  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Способы компиляции определенных частей кода.  
  
 [Построение и очистка проектов и решений в Visual Studio](https://docs.microsoft.com/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 В этой статье описывается организация состава отдельных сборок, изменение свойств проекта и убедитесь, что построение проектов в правильном порядке.
