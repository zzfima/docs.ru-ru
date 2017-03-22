---
title: "/ noconfig | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 304d0e7fc787adb1d7776a2c047090ffc230fcc1
ms.lasthandoff: 03/13/2017

---
# <a name="noconfig"></a>/noconfig
Указывает, что компилятор не должен ссылаться автоматически часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки или импорт `System` и `Microsoft.VisualBasic` пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 `/noconfig` Параметр указывает компилятору не компилировать с использованием файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe. Файл Vbc.rsp ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен. Компилятор неявно ссылается на сборку System.dll, если `/nostdlib` параметра. `/nostdlib` Параметр указывает компилятору не компилировать с Vbc или автоматически ссылаться на сборки System.dll.  
  
> [!NOTE]
>  Сборки Mscorlib.dll и Microsoft.VisualBasic.dll всегда имеется ссылка.  
  
 Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `/noconfig` параметр). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, передаваемые `vbc` последней команды. Таким образом любой параметр в командной строке переопределяет настройки того же параметра в файле Vbc.rsp.  
  
> [!NOTE]
>  `/noconfig` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [/ nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ (Указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
