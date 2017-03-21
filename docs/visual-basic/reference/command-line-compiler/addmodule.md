---
title: "/ addmodule | Документы Microsoft"
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
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 949962905ec933dc42301bf8c21654e73dbe2f70
ms.lasthandoff: 03/13/2017

---
# <a name="addmodule"></a>/addmodule
Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Разделенный запятыми список файлов, которые содержат метаданные, но не содержат манифестов сборки. Имена файлов, содержащие пробелы, которые должны быть заключены в кавычки (» «).  
  
## <a name="remarks"></a>Примечания  
 Файлы, упорядоченные по `fileList` параметр должен быть создан с `/target:module` параметр, или с другим компилятором эквивалентно `/target:module`.  
  
 Все модули, добавленные с помощью `/addmodule` во время выполнения должны находиться в том же каталоге, что и выходной файл. То есть во время компиляции можно указать модуль в любой папке, но во время выполнения он должен находиться в каталоге приложения. Если это не так, вы получаете <xref:System.TypeLoadException>ошибка.</xref:System.TypeLoadException>  
  
 При указании (явно или неявно) любой[/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) отличный вариант `/target:module` с `/addmodule`, можно передать файлы `/addmodule` становятся частью сборки проекта. Сборки, необходимые для выполнения выходного файла, который имеет один или добавлены дополнительные файлы `/addmodule`.  
  
 Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
>  `/addmodule` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 В следующем коде создается модуль.  
  
 [!code-vb[VbVbalrCompiler&#47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler&#48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 При запуске `t1`, он выводит `802`.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
