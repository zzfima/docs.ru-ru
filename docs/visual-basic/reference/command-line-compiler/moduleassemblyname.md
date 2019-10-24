---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775625"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Задает имя сборки, частью которой будет этот модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`assembly_name`|Имя сборки, частью которой будет этот модуль.|  
  
## <a name="remarks"></a>Заметки  
 Компилятор обрабатывает параметр `-moduleassemblyname` только в том случае, если был указан параметр `-target:module`. В результате компилятор создаст модуль. Модуль, созданный компилятором, действителен только для сборки, указанной с помощью параметра `-moduleassemblyname`. Если модуль размещается в другой сборке, возникнут ошибки во время выполнения.  
  
 Параметр `-moduleassemblyname` требуется только в том случае, если выполняются следующие условия.  
  
- Для типа данных в модуле требуется доступ к типу `Friend` в сборке, на которую указывает ссылка.  
  
- Сборка, на которую указывает ссылка, предоставила дружественной сборке доступ к сборке, в которую будет построен модуль.  
  
 Дополнительные сведения о создании модуля см. в разделе [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Дополнительные сведения о дружественных сборках см. в разделе [дружественные сборки](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> Параметр `-moduleassemblyname` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание многофайловой сборки](../../../framework/app-domains/build-multifile-assembly.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Дружественные сборки](../../../standard/assembly/friend.md)
