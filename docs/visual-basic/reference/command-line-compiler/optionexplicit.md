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
ms.openlocfilehash: 5c0946b94bfe02d797d1a484088869375703eb6a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005305"
---
# <a name="-optionexplicit"></a>-optionexplicit
Приводит к тому, что компилятор сообщает об ошибках, если переменные не объявляются до их использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Укажите `-optionexplicit+`, чтобы требовать явного объявления переменных. Параметр `-optionexplicit+` используется по умолчанию и совпадает с `-optionexplicit`. Параметр `-optionexplicit-` включает неявное объявление переменных.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), инструкция переопределяет параметр компилятора командной строки `-optionexplicit`.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Установка параметра-оптионексплиЦит в интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.   
  
2. Откройте вкладку **Компиляция**.  
  
3. Измените значение в поле " **явный** ".  
  
## <a name="example"></a>Пример  
 Следующий код компилируется при использовании `-optionexplicit-`.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
