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
ms.openlocfilehash: e7dbc4d5f06096978c4d93ea20677dcb60bc3fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-optioninfer"></a>-optioninfer
Включает использование локального определения типов в различных объявлениях.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный. Укажите `-optioninfer+`, чтобы включить локальное определение типов, или `-optioninfer-`, чтобы заблокировать его. Параметр `-optioninfer`, для которого не указано значение, действует так же, как `-optioninfer+`. Значение по умолчанию при отсутствии параметра `-optioninfer` также равно `-optioninfer+`. Значение по умолчанию задается в файле ответов Vbc.rsp.|  
  
> [!NOTE]
>  Можно использовать параметр `-noconfig`, чтобы сохранить внутренние значения компилятора по умолчанию вместо использования значений, заданных в vbc.rsp. Значение компилятора по умолчанию для этого параметра — `-optioninfer-`.  
  
## <a name="remarks"></a>Примечания  
 Если файл исходного кода содержит [Option Infer-оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md), переопределяет инструкцию `-optioninfer` параметр компилятора командной строки.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>Чтобы задать - optioninfer в Интегрированной среде разработки Visual Studio  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2.  На **компиляции** измените значение в **Option infer** поле.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `test.vb` с включенным локальным определением типов.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
