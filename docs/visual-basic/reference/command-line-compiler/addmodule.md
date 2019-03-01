---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 5a6d367f4b09de600bb744aa2abed0da2c93aa0b
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202370"
---
# <a name="-addmodule"></a>-addmodule
Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Разделенный запятыми список файлов, которые содержат метаданные, но не содержат манифестов сборки. Имена файлов, содержащие пробелы, которые должны быть заключены в кавычки (» «).  
  
## <a name="remarks"></a>Примечания  
 Файлы, упорядоченные по `fileList` параметр должен быть создан с `-target:module` параметр, или с помощью другого компилятора эквивалентно `-target:module`.  
  
 Все модули, добавленные с помощью `-addmodule` во время выполнения должны находиться в том же каталоге, что и выходной файл. То есть можно указать модуль в любом каталоге во время компиляции, но во время выполнения он должен находиться в каталоге приложения. Если это не так, вы получаете <xref:System.TypeLoadException> ошибки.  
  
 При указании (явно или неявно) любой[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) параметра, отличное от `-target:module` с `-addmodule`, файлов, передаваемый `-addmodule` становятся частью сборки проекта. Сборка необходима для проведения выходной файл, который имеет один или добавить дополнительные файлы с `-addmodule`.  
  
 Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
>  `-addmodule` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 В следующем коде создается модуль.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 При запуске `t1`, он выводит `802`.  
  
## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-ссылке (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
