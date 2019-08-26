---
title: -pdb (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 3081f4716e8cd858d789db6050e635af941aa05c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602575"
---
# <a name="-pdb-c-compiler-options"></a>-pdb (параметры компилятора C#)
Параметр компилятора **-pdb** задает имя и расположение файла отладочных символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя и расположение файла отладочных символов.  
  
## <a name="remarks"></a>Примечания  
 Если указан параметр [-debug (параметры компилятора C#)](./debug-compiler-option.md), компилятор создаст в каталоге с выходным файлом (EXE или DLL) PDB-файл с тем же именем.  
  
 С помощью параметра **-pdb** можно задать имя PDB-файла, отличающееся от используемого по умолчанию.  
  
 Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.  
  
## <a name="example"></a>Пример  
 Компиляция файла `t.cs` и создание файла tt.pdb:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](./index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
