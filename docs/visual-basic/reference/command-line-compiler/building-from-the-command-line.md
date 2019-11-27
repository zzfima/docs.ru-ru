---
title: Построение из командной строки
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
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344797"
---
# <a name="building-from-the-command-line-visual-basic"></a>Построение из командной строки (Visual Basic)

Проект Visual Basic состоит из одного или нескольких отдельных исходных файлов. В ходе процесса, известного как компиляция, эти файлы объединяются в один пакет — один исполняемый файл, который можно запустить как приложение.

Visual Basic предоставляет компилятор командной строки в качестве альтернативы компиляции программ из интегрированной среды разработки (IDE) Visual Studio. Компилятор командной строки предназначен для ситуаций, в которых не требуется полный набор функций в интегрированной среде разработки (например, при использовании или записи для компьютеров с ограниченным объемом системной памяти или дискового пространства).

Чтобы скомпилировать исходные файлы в интегрированной среде разработки Visual Studio, выберите команду **построить** в меню **Сборка** .

> [!TIP]
> При создании файлов проекта с помощью интегрированной среды разработки Visual Studio можно отобразить сведения о соответствующей команде **vbc** и ее параметрах в окне вывода. Чтобы отобразить эти сведения, откройте [диалоговое окно Параметры, проекты и решения, сборка и запуск](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), а затем задайте для параметра **уровень детализации выходных данных сборки проекта MSBuild** значение **обычное** или более высокий уровень детализации. Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).

Файлы проекта (VBPROJ) можно компилировать в командной строке с помощью MSBuild. Дополнительные сведения см. в разделе [Справочник по командной строке](/visualstudio/msbuild/msbuild-command-line-reference) и [Пошаговое руководство. Использование MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).

## <a name="in-this-section"></a>В этом разделе

[Как вызвать компилятор командной строки](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) \
Описание вызова компилятора командной строки в командной строке MS-DOS или в определенном подкаталоге.

[Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) \
Содержит список примеров командных строк, которые можно изменить для собственного использования.

## <a name="related-sections"></a>Связанные разделы

[Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md) \
Предоставляет списки параметров компилятора, упорядоченные в алфавитном порядке или по назначению.

 \ [условной компиляции](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
Описывает, как компилировать определенные фрагменты кода.

[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \ (Построение и очистка проектов и решений в Visual Studio)
Описывается способ организации того, что будет включаться в разные сборки, выберите Свойства проекта и убедитесь, что проекты строятся в правильном порядке.
