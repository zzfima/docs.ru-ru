---
title: "-target:module (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b54ea9085ecc23d4a535d440d0634c997f22615
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="targetmodule-c-compiler-options"></a>/target:module (параметры компилятора C#)
Этот параметр указывает компилятору не создавать манифест сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/target:module  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию выходной файл, созданный при компиляции с этим параметром, имеет расширение .netmodule.  
  
 Файл без манифеста сборки не может быть загружен в общеязыковую среду выполнения .NET Framework. Тем не менее его можно включить в манифест сборки с помощью параметра [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Если в рамках одной процедуры компиляции создается несколько модулей, типы [internal](../../../csharp/language-reference/keywords/internal.md) из одного модуля будут доступны для других модулей, компилируемых вместе с ним. Если код одного модуля ссылается на типы `internal` в другом модуле, оба модуля необходимо включить в манифест сборки с помощью параметра **/addmodule**.  
  
 Создание модуля в среде разработки Visual Studio не поддерживается.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция файла`in.cs`, создание модуля `in.netmodule`:  
  
```console  
csc /target:module in.cs  
```  
  
## <a name="see-also"></a>См. также  
 [/ Target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
