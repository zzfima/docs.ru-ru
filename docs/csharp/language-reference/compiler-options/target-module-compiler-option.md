---
title: -target:module (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: d02a46390ca34b8063320df6ec237a00c0423c88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-targetmodule-c-compiler-options"></a>-target:module (параметры компилятора C#)
Этот параметр указывает компилятору не создавать манифест сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию выходной файл, созданный при компиляции с этим параметром, имеет расширение .netmodule.  
  
 Файл без манифеста сборки не может быть загружен в общеязыковую среду выполнения .NET Framework. Тем не менее его можно включить в манифест сборки с помощью параметра [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Если в рамках одной процедуры компиляции создается несколько модулей, типы [internal](../../../csharp/language-reference/keywords/internal.md) из одного модуля будут доступны для других модулей, компилируемых вместе с ним. Если код одного модуля ссылается на типы `internal` в другом модуле, оба модуля нужно включить в манифест сборки с помощью параметра **-addmodule**.  
  
 Создание модуля в среде разработки Visual Studio не поддерживается.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция файла`in.cs`, создание модуля `in.netmodule`:  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [-target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
