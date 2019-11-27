---
title: Примеры командных строк компиляции
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350851"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Примеры командных строк компиляции (Visual Basic)

В качестве альтернативы компиляции Visual Basic программ из Visual Studio можно выполнить компиляцию из командной строки, чтобы создать исполняемые файлы (exe) или файлы библиотеки динамической компоновки (DLL).

Компилятор командной строки Visual Basic поддерживает полный набор параметров, управляющих входными и выходными файлами, сборками, параметрами отладки и препроцессором. Каждый параметр доступен в двух взаимозаменяемых формах: `-option` и `/option`. В этой документации показана только форма `-option`.

В следующей таблице перечислены некоторые примеры командных строк, которые можно изменить для собственного использования.

|Чтобы|Чтобы подключить или изменить свойства уже подключенной группы управления, используйте узел|
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
