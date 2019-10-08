---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: c6fc7e9dcfbce938ad75b0f357c2bfa9cd10703a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005322"
---
# <a name="-optioninfer"></a>-optioninfer
Включает использование локального определения типов в различных объявлениях.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный параметр. Укажите `-optioninfer+`, чтобы включить локальное определение типов, или `-optioninfer-`, чтобы заблокировать его. Параметр `-optioninfer`, для которого не указано значение, действует так же, как `-optioninfer+`. Значение по умолчанию при отсутствии параметра `-optioninfer` также равно `-optioninfer+`. Значение по умолчанию задается в файле ответов Vbc.rsp.|  
  
> [!NOTE]
> Можно использовать параметр `-noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp. Значение компилятора по умолчанию для этого параметра — `-optioninfer-`.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [инструкцию Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md), инструкция переопределяет параметр компилятора командной строки `-optioninfer`.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>Установка параметра-оптионинфер в интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозреватель решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. На вкладке **Компиляция** измените значение в поле **параметр Infer** .  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `test.vb` с включенным локальным определением типов.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
