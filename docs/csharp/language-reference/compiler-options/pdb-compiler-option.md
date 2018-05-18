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
ms.openlocfilehash: 9f8158ec0d8de2b9249c4f69830c37480c34b390
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
 Если указан параметр [-debug (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), компилятор создаст в каталоге с выходным файлом (EXE или DLL) PDB-файл с тем же именем.  
  
 С помощью параметра **-pdb** можно задать имя PDB-файла, отличающееся от используемого по умолчанию.  
  
 Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.  
  
## <a name="example"></a>Пример  
 Компиляция файла `t.cs` и создание файла tt.pdb:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
