---
title: "/ sdkpath | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3584daa49bca699f022a1afd34e3d450b8442060
ms.lasthandoff: 03/13/2017

---
# <a name="sdkpath"></a>/sdkpath
Задает расположение библиотек mscorlib.dll и microsoft.visualbasic.dll.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a>Аргументы  
 `path`  
 Каталог, содержащий версии Mscorlib.dll и Microsoft.VisualBasic.dll, используемые при компиляции. Этот путь не проверяется до загрузки. Заключите имя каталога в кавычки (» «), если он содержит пробел.  
  
## <a name="remarks"></a>Примечания  
 Этот параметр указывает [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятору загрузить файлы Mscorlib.dll и Microsoft.VisualBasic.dll из расположения, не по умолчанию. `/sdkpath` Параметр был разработан для использования с [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] Применяются различные версии поддерживаемых библиотек, чтобы избежать использования типов и функций языка не найден на устройствах.  
  
> [!NOTE]
>  `/sdkpath` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки. `/sdkpath` Параметр задается при [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] загрузке проекта устройства.  
  
 Можно указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью `/vbruntime` параметр компилятора. Дополнительные сведения см. в разделе [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], с помощью версии Mscorlib.dll и Microsoft.VisualBasic.dll найти в каталоге установки по умолчанию [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] на диске C:. Как правило, используется последней версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/ netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)   
 [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
