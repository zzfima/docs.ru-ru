---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: fbe3634d1fbc03acd56ef7276d65fd54493b9806
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002416"
---
# <a name="-addmodule"></a>-addmodule
Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Разделенный запятыми список файлов, содержащих метаданные, но не содержащих Манифесты сборки. Имена файлов, содержащие пробелы, должны быть заключены в кавычки ("").  
  
## <a name="remarks"></a>Примечания  
 Файлы, перечисленные в параметре `fileList`, должны быть созданы с параметром `-target:module` или с помощью другого компилятора, эквивалентного `-target:module`.  
  
 Все модули, добавленные с помощью `-addmodule`, должны находиться в одном каталоге с выходным файлом во время выполнения. Это значит, что модуль можно указать в любом каталоге во время компиляции, но во время выполнения модуль должен находиться в каталоге приложения. Если это не так, возникает ошибка <xref:System.TypeLoadException>.  
  
 При указании (неявно или явно) любого[целевого параметра (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) , отличного от `-target:module` с `-addmodule`, файлы, передаваемые в `-addmodule`, становятся частью сборки проекта. Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных с помощью `-addmodule`.  
  
 Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
> Параметр `-addmodule` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код создает модуль.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 При запуске `t1` выводится `802`.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
