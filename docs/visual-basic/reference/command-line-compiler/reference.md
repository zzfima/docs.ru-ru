---
title: -ссылке (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb5d3b4c50a9c22880bdcc8406835cf51481e3cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-reference-visual-basic"></a>-ссылке (Visual Basic)
Указывает компилятору на необходимость сделать сведения о типе в указанных сборках доступными для проекта, которые в настоящее время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileList`|Обязательно. Список всех имен файлов сборки, разделенных запятыми. Если имя файла содержит пробел, заключите его в кавычки.|  
  
## <a name="remarks"></a>Примечания  
 Импортируемые файлы должны содержать метаданные сборки. Только открытые типы являются видимыми за пределами сборки. [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.  
  
 При ссылках на сборки (сборка A), который в свою очередь ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б, если:  
  
-   Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.  
  
-   Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.  
  
 Используйте [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) для указания каталога, в котором находится один или несколько ссылок на сборки.  
  
 Компилятор должен распознавать тип в сборке (не в модуле) он должен иметь возможность для разрешения типа. Как это можно сделать одним из примеров является определение экземпляра типа. Существуют другие способы для разрешения имен типов в сборке, компилятор. Например при наследовании из типа в сборке, имя типа затем становится известно компилятору.  
  
 Файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборок, используемых по умолчанию. Использовать `-noconfig` запретить компилятору использовать файл Vbc.rsp.  
  
 Краткой формой `-reference` является `/r`.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует исходный файл `Input.vb` и ссылки на сборки из `Metad1.dll` и `Metad2.dll` для создания `Out.exe`.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
