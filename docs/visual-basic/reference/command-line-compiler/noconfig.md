---
title: /noconfig
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94d13ccf0168027f4560b980c41e2a001ff503fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig"></a>/noconfig
Указывает, что компилятор не должен ссылаться автоматически часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки или импорта `System` и `Microsoft.VisualBasic` пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 `/noconfig` Параметр предписывает компилятору не компилировать с использованием файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe. Файл Vbc.rsp ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен. Компилятор неявно ссылается на сборку System.dll, если не `/nostdlib` параметра. `/nostdlib` Параметр предписывает компилятору не компилировать с Vbc.rsp или автоматически ссылку на сборку System.dll.  
  
> [!NOTE]
>  Всегда создаются ссылки на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
 Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `/noconfig` параметр). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, передаваемые `vbc` последней команды. Таким образом любой параметр командной строки переопределяет параметр того же параметра в файле Vbc.rsp.  
  
> [!NOTE]
>  `/noconfig` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [/ nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
