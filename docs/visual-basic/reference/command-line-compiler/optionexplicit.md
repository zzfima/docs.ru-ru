---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332395"
---
# <a name="-optionexplicit"></a>-optionexplicit
Указывает компилятору для сообщения об ошибках, если переменные не объявлены, прежде чем они используются.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Укажите `-optionexplicit+` требуется явное объявление переменных. `-optionexplicit+` — Это значение по умолчанию, так же, как `-optionexplicit`. `-optionexplicit-` Позволяет неявное объявление переменных.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), то оператор переопределяет `-optionexplicit` параметр компилятора командной строки.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Чтобы задать - optionexplicit в Интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.   
  
2. Откройте вкладку **Компиляция**.  
  
3. Измените значение в **Option Explicit** поле.  
  
## <a name="example"></a>Пример  
 Следующий код компилируется при `-optionexplicit-` используется.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
