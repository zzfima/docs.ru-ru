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
ms.openlocfilehash: b7879c23bc64269c793c21b61b84d6f0fd4bdc24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046283"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)

В качестве альтернативы компиляции Visual Basic программ из Visual Studio можно выполнить компиляцию из командной строки, чтобы создать исполняемые файлы (exe) или файлы библиотеки динамической компоновки (DLL).

Компилятор командной строки Visual Basic поддерживает полный набор параметров, управляющих входными и выходными файлами, сборками, параметрами отладки и препроцессором. Каждый параметр доступен в двух взаимозаменяемых формах: `-option` и. `/option` В `-option` этой документации показана только форма.

В следующей таблице перечислены некоторые примеры командных строк, которые можно изменить для собственного использования.

|Кому|Использовать|
|--------|---------|
|Скомпилируйте файл File. vb и создайте файл. exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|Скомпилируйте файл File. vb и создайте файл. dll|`vbc -target:library File.vb`|
|Скомпилируйте файл File. vb и создайте My. exe|`vbc -out:My.exe File.vb`|
|Скомпилируйте файл File. vb и создайте библиотеку и ссылочную сборку с именем file. dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Компилировать все файлы Visual Basic в текущем каталоге с оптимизацией и `DEBUG` определенным символом, создавая file2. exe.|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Компилировать все файлы Visual Basic в текущем каталоге, создавая отладочную версию file2. DLL без отображения логотипа или предупреждений|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Компилировать все файлы Visual Basic в текущем каталоге в файл. dll|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> При построении проекта с помощью интегрированной среды разработки Visual Studio можно отобразить сведения о связанной команде **vbc** с ее параметрами компилятора в окне вывода. Чтобы отобразить эти сведения, откройте [диалоговое окно Параметры, проекты и решения, сборка и запуск](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), а затем задайте для параметра **уровень детализации выходных данных сборки проекта MSBuild** значение **обычное** или более высокий уровень детализации.

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
