---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336087"
---
# <a name="-optionstrict"></a>-optionstrict
Требовать строгой семантики для ограничения неявного преобразования типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. `-optionstrict+` Ограничивает неявное преобразование типов. Значение по умолчанию для этого параметра — `-optionstrict-`. `-optionstrict+` Параметр совпадает со значением `-optionstrict`. Можно использовать как для разрешающей семантики.  
  
 `custom`  
 Обязательный. Предупреждать, когда не накладывается ограничение на строгую семантику языка.  
  
## <a name="remarks"></a>Примечания  
 Когда `-optionstrict+` по сути, является неявно могут выполняться только расширяющие преобразования типа. Неявные преобразования типов, например назначение `Decimal` введите в объект типа integer, которые выводятся как ошибки.  
  
 Чтобы создать предупреждения для неявных сужающих преобразований типа, используйте `-optionstrict:custom`. Используйте `-nowarn:numberlist` для игнорирования определенных предупреждений и `-warnaserror:numberlist` для конкретного предупреждения обрабатываются как ошибки.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Чтобы задать - optionstrict в Интегрированной среде разработки Visual Studio  
  
1. Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства.**   
  
2. Откройте вкладку **Компиляция**.  
  
3. Измените значение в **Option Strict** поле.  
  
### <a name="to-set--optionstrict-programmatically"></a>Чтобы установить - optionstrict программными средствами  
  
-   См. в разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Test.vb` с помощью строгой семантики.  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
