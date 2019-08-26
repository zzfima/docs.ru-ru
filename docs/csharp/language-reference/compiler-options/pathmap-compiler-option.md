---
title: -pathmap (параметры компилятора C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 48e96d2ec2ccbea83d573c0eb3630b1591c407a9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606624"
---
# <a name="-pathmap-c-compiler-options"></a>-pathmap (параметры компилятора C#)

Параметр компилятора **-pathmap** определяет способ сопоставления физических путей и выходных имен исходных путей компилятором.

## <a name="syntax"></a>Синтаксис

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a>Аргументы

 `path1` — полный путь к исходным файлам в текущем окружении.

 `sourcePath1` — исходный путь подставляется вместо `path1` в любых выходных файлах.

Чтобы указать несколько сопоставленных исходных путей, разделите их запятыми.

## <a name="remarks"></a>Примечания

Компилятор записывает исходный путь в выходные данные по следующим причинам:

1. Исходный путь подставляется вместо аргумента, когда <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> применяется как необязательный параметр.
1. Исходный путь внедряется как PDB-файл.
1. Путь к PDB-файлу внедряется в PE-файл (переносимый исполняемый файл).

Этот параметр сопоставляет каждый физический путь на компьютере, где выполняется компилятор, с соответствующим путем, который должен быть записан в выходные файлы.

## <a name="example"></a>Пример

Компиляция `t.cs` в каталоге **C:\\work\\tests** и сопоставление этого каталога с каталогом **\publish** в выходных данных:

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](./index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
