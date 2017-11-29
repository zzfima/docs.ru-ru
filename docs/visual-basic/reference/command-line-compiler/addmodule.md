---
title: /addmodule
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fff292605e125776ae25e667d4813d770ed0a0aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 Файлы, перечисленные по `fileList` параметр должен быть создан с `/target:module` параметр, или с помощью другого компилятора эквивалентно `/target:module`.  
  
 Все модули, добавленные с `/addmodule` должно быть в том же каталоге, как выходного файла во время выполнения. То есть можно указать модуль в любом каталоге во время компиляции, но во время выполнения он должен находиться в каталоге приложения. Если это не так, вы получаете <xref:System.TypeLoadException> ошибки.  
  
 При указании (явно или неявно) любой[/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) параметр, отличный от `/target:module` с `/addmodule`, передаются файлы `/addmodule` становятся частью сборки проекта. Сборки, необходимые для выполнения выходного файла, который имеет один или несколько файлов добавлены, `/addmodule`.  
  
 Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
>  `/addmodule` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 В следующем коде создается модуль.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 При запуске `t1`, он выводит `802`.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
