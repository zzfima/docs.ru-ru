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
ms.openlocfilehash: 21efca701eb16898dd291d73bf0431641ba75d12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788886"
---
# <a name="-reference-visual-basic"></a>-ссылке (Visual Basic)
Указывает компилятору сделать сведения о типе в указанных сборках доступными для компилируемого проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileList`|Обязательный. Список всех имен файлов сборки, разделенных запятыми. Если имя файла содержит пробел, заключите его в кавычки.|  
  
## <a name="remarks"></a>Примечания  
 Импортируемые файлы должны содержать метаданные сборки. Только открытые типы являются видимыми вне сборки. [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) параметр импортирует метаданные из модуля.  
  
 При ссылке на сборку (сборку А) которая сама ссылается на другую сборку (сборку Б), необходимо ссылаться на сборку Б, если:  
  
- Тип из сборки A наследуется из типа или реализует интерфейс сборки Б.  
  
- Вызывается поле, свойство, событие или метод, имеющий тип возвращаемого значения или тип параметра из сборки Б.  
  
 Используйте [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) для указания каталога, в котором находится один или несколько ссылок на сборки.  
  
 Для компилятора распознавать тип в сборке (не в модуле) он должен иметь возможность разрешать типы. Как это можно сделать одним из примеров является определение экземпляра типа. Другие способы доступны для разрешения имен типов в сборки для компилятора. Например при наследовании из типа в сборке, имя типа затем становится известно компилятору.  
  
 Файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки, используется по умолчанию. Использовать `-noconfig` запретить компилятору использовать файл Vbc.rsp.  
  
 Краткой формой `-reference` является `/r`.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует исходный файл `Input.vb` и ссылочные сборки из `Metad1.dll` и `Metad2.dll` для создания `Out.exe`.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
