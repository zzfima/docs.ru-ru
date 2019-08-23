---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 052d6937846df39bd94d532e1b63ebe522dbf6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964680"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Задает имя сборки, частью которой будет этот модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`assembly_name`|Имя сборки, частью которой будет этот модуль.|  
  
## <a name="remarks"></a>Примечания  
 Компилятор обрабатывает `-moduleassemblyname` параметр, только `-target:module` если указан параметр. В результате компилятор создаст модуль. Модуль, созданный компилятором, действителен только для сборки, указанной с помощью `-moduleassemblyname` параметра. Если модуль размещается в другой сборке, возникнут ошибки во время выполнения.  
  
 Этот `-moduleassemblyname` параметр необходим только в том случае, если выполняются следующие условия.  
  
- Для типа данных в модуле требуется доступ к `Friend` типу в сборке, на которую имеется ссылка.  
  
- Сборка, на которую указывает ссылка, предоставила дружественной сборке доступ к сборке, в которую будет построен модуль.  
  
 Дополнительные сведения о создании модуля см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Дополнительные сведения о дружественных сборках см. в разделе [дружественные сборки](../../../standard/assembly/friend-assemblies.md).  
  
> [!NOTE]
> Этот `-moduleassemblyname` параметр недоступен в среде разработки Visual Studio. он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание многофайловой сборки](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Дружественные сборки](../../../standard/assembly/friend-assemblies.md)
