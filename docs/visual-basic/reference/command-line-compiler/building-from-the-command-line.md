---
title: Построение из командной строки (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 89bcd6e0e7c1cc867bf853dc9bbe96628942ace2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078946"
---
# <a name="building-from-the-command-line-visual-basic"></a>Построение из командной строки (Visual Basic)
Проект Visual Basic состоит из одного или нескольких файлов отдельный источник. В процессе компиляции эти файлы соединяются в один пакет — исполняемый файл, который запускается как приложение.  
  
 Visual Basic предоставляет компилятора командной строки в качестве альтернативы компиляции программ из Интегрированной среды разработки Visual Studio. Компилятор командной строки предназначен для ситуаций, в которых вам не требуется полный набор функций в интегрированной среде разработки, например, при использовании или запись для компьютеров с помощью ограниченных системных памяти или дисковое пространство.  
  
  Для компиляции исходных файлов из интегрированной среды разработки Visual Studio, выберите **построения** команду **построения** меню.  
  
> [!TIP]
>  При построении проекта файлы с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** команду и ее параметры в окне вывода. Чтобы отобразить эту информацию, откройте [диалоговое окно "Параметры", проекты и решения, построения и выполнения](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **степень подробности сообщений при сборке проекта MSBuild** для **обычный** или более высокий уровень детализации. Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 Файлы проекта (VBPROJ) в командной строке можно скомпилировать с помощью MSBuild. Дополнительные сведения см. в разделе [справочнике по командной строке](/visualstudio/msbuild/msbuild-command-line-reference) и [Пошаговое руководство: использование MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Вызов компилятора командной строки](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 В этой статье описывается вызов компилятора командной строки в командную строку или из определенной папки.  
  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Предоставляет список примеры командных строк, которые можно изменить для собственного использования.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 Предоставляет список параметров компилятора, упорядоченные по алфавиту или по назначению.  
  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Описывает процедуру компиляции определенных частей кода.  
  
 [Построение и очистка проектов и решений в Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Описывает способ организации будут включены в каждой из них, выберите свойства проекта и убедитесь, что сборка проектов в правильном порядке.
