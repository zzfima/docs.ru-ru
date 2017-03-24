---
title: "/ nostdlib (Visual Basic) | Документы Microsoft"
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
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 3bacd7d51d12ec6c48dc11ff4b83d842a9e78a30
ms.lasthandoff: 03/13/2017

---
# <a name="nostdlib-visual-basic"></a>/nostdlib (Visual Basic)
Указывает компилятору не ссылаться на стандартные библиотеки автоматически.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a>Примечания  
 `/nostdlib` Удаляет автоматическую ссылку на сборку System.dll и предотвращает чтение файла Vbc.rsp компилятор. Файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe — ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен.  
  
> [!NOTE]
>  Сборки Mscorlib.dll и Microsoft.VisualBasic.dll всегда имеется ссылка.  
  
> [!NOTE]
>  `/nostdlib` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` без ссылок на стандартные библиотеки. Необходимо задать `_MYTYPE` константы условной компиляции, в строку «Пустой» для удаления `My` объекта.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
