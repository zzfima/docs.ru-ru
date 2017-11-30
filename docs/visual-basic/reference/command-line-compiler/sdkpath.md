---
title: /sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 876922385124db3e8db12c93c75194da83d2526c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sdkpath"></a>/sdkpath
Задает расположение библиотек mscorlib.dll и microsoft.visualbasic.dll.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a>Аргументы  
 `path`  
 Каталог, содержащий версии Mscorlib.dll и Microsoft.VisualBasic.dll, используемые при компиляции. Этот путь не проверяется до загрузки. Заключите имя каталога в кавычки (» «), если он содержит пробелы.  
  
## <a name="remarks"></a>Примечания  
 При выборе этого параметра [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятора для загрузки из нестандартное расположение файлы Mscorlib.dll и Microsoft.VisualBasic.dll. `/sdkpath` Параметр был разработан для использования с [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). [!INCLUDE[Compact](~/includes/compact-md.md)] Применяются различные версии поддерживаемых библиотек, чтобы избежать использования типы и функции языка, не найден на устройствах.  
  
> [!NOTE]
>  `/sdkpath` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки. `/sdkpath` Параметр задан, если [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] загрузке проекта устройства.  
  
 Можно указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью `/vbruntime` параметр компилятора. Дополнительные сведения см. в разделе [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии Mscorlib.dll и Microsoft.VisualBasic.dll найден в каталоге установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C. Обычно, следует использовать самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
