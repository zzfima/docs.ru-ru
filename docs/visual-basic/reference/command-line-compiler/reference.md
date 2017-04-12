---
title: "/ Reference (Visual Basic) | Документы Microsoft"
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
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
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
ms.openlocfilehash: 12344dba82131d6be2c32127de287a6e9e3efa39
ms.lasthandoff: 03/13/2017

---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
Указывает компилятору сделать доступными для проекта, компилируемого в данный момент сведения о типе в указанных сборках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileList`|Обязательный. Разделенный запятыми список имен файлов сборки. Если имя файла содержит пробел, заключите имя в кавычки.|  
  
## <a name="remarks"></a>Примечания  
 Импортируемые файлы должны содержать метаданные сборки. Только открытые типы видимы за пределами сборки. [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.  
  
 При ссылке на сборки (сборка A), которая сама ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б, если:  
  
-   Из сборки A тип наследуется от типа или реализует интерфейс из сборки б.  
  
-   Вызывается поле, свойство, событие или метод, который имеет возвращаемый тип или параметр типа из сборки Б.  
  
 Используйте [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) указать каталог, в котором находится один или несколько ссылки на сборки.  
  
 Компилятор мог распознавать тип в сборке (не в модуле) он должен иметь возможность разрешать типы. Одним из примеров того, как это можно сделать является определение экземпляра типа. Другие способы доступны для разрешения имен типов в сборке для компилятора. Например при наследовании от типа в сборке, имя типа затем становится известно компилятору.  
  
 Файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборок, используемых по умолчанию. Используйте `/noconfig` , если не нужно, чтобы компилятор использовал файл Vbc.rsp.  
  
 Краткая форма `/reference` — `/r`.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует источник файла я`nput.vb` и ссылаться на сборки из M`etad1.dll` и M`etad2.dll` производить O`ut.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
