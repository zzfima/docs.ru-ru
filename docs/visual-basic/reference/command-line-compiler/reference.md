---
title: /reference (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f8c6851802afa818cc80b3f6d7eafc2ef47ac689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
Указывает компилятору на необходимость сделать сведения о типе в указанных сборках доступными для проекта, которые в настоящее время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileList`|Обязательный. Список всех имен файлов сборки, разделенных запятыми. Если имя файла содержит пробел, заключите его в кавычки.|  
  
## <a name="remarks"></a>Примечания  
 Импортируемые файлы должны содержать метаданные сборки. Только открытые типы являются видимыми за пределами сборки. [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.  
  
 При ссылках на сборки (сборка A), который в свою очередь ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б, если:  
  
-   Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.  
  
-   Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.  
  
 Используйте [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) для указания каталога, в котором находится один или несколько ссылок на сборки.  
  
 Компилятор должен распознавать тип в сборке (не в модуле) он должен иметь возможность для разрешения типа. Как это можно сделать одним из примеров является определение экземпляра типа. Существуют другие способы для разрешения имен типов в сборке, компилятор. Например при наследовании из типа в сборке, имя типа затем становится известно компилятору.  
  
 Файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборок, используемых по умолчанию. Использовать `/noconfig` запретить компилятору использовать файл Vbc.rsp.  
  
 Краткой формой `/reference` является `/r`.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `Input.vb` и ссылочные сборки из `Metad1.dll` и `Metad2.dll` и создает, таким образом, файл `Out.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
