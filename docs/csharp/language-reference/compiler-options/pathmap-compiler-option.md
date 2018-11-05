---
title: -pathmap (параметры компилятора C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: abcc67a16e257a15599431a8fefe7753e6d52549
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190324"
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

- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
