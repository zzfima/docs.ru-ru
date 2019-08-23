---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 0e0915a2534f950cec074632a59750c3f96b679d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962457"
---
# <a name="-addmodule"></a>-addmodule
Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Разделенный запятыми список файлов, содержащих метаданные, но не содержащих Манифесты сборки. Имена файлов, содержащие пробелы, должны быть заключены в кавычки ("").  
  
## <a name="remarks"></a>Примечания  
 Файлы, перечисленные в `fileList` параметре, должны быть созданы `-target:module` с параметром или с `-target:module`другим эквивалентом компилятора.  
  
 Все модули, добавленные с помощью `-addmodule` , должны находиться в одном каталоге с выходным файлом во время выполнения. Это значит, что модуль можно указать в любом каталоге во время компиляции, но во время выполнения модуль должен находиться в каталоге приложения. Если это не так, <xref:System.TypeLoadException> возникает ошибка.  
  
 При указании (неявно или явно) любого[целевого параметра (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) `-addmodule`, отличного от `-target:module` , передаваемые `-addmodule` файлы становятся частью сборки проекта. Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных `-addmodule`с помощью.  
  
 Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
> Этот `-addmodule` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код создает модуль.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 При запуске `t1`он выводит `802`.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
