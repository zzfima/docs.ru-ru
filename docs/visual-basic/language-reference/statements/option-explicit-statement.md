---
title: Оператор Option Explicit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 0a319ba4259e66ed9a37aa2de9e97d2335b78663
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308618"
---
# <a name="option-explicit-statement-visual-basic"></a>Оператор Option Explicit (Visual Basic)
Принудительное явное объявление всех переменных в файле или неявного объявления переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Части  
 `On`  
 Необязательный параметр. Позволяет `Option Explicit` проверки. Если `On` или `Off` не указан, по умолчанию используется `On`.  
  
 `Off`  
 Необязательный параметр. Отключает `Option Explicit` проверки.  
  
## <a name="remarks"></a>Примечания  
 Когда `Option Explicit On` или `Option Explicit` появится в файле, необходимо явно объявить все переменные с помощью `Dim` или `ReDim` инструкций. Если вы попытаетесь использовать необъявленных переменных, возникает ошибка во время компиляции. `Option Explicit Off` Оператор обеспечивает неявное объявление переменных.  
  
 Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.  
  
> [!NOTE]
>  Установка `Option Explicit` для `Off` обычно не является хорошей практикой. Вы можете допустить ошибку при вводе имени переменной в одном или нескольких местах, что приведет к непредвиденным результатам при выполнении программы.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Если оператор Option Explicit отсутствует  
 Если исходный код не содержит `Option Explicit` инструкции **Option Explicit** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. Если используется компилятор командной строки, [дополнительные](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) используется параметр компилятора.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Чтобы задать Option Explicit в интегрированной среде разработки  
  
1. Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Откройте вкладку **Компиляция**.  
  
3. Задайте значение в **Option Explicit** поле.  
  
 При создании нового проекта, **Option Explicit** на **компиляции** набор вкладок **Option Explicit** в **Visual Basic по умолчанию**диалоговое окно. Чтобы получить доступ к **Visual Basic по умолчанию** диалоговом окне **средства** меню, щелкните **параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальная настройка по умолчанию в **параметры Visualbasic по умолчанию** является `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Чтобы задать Option Explicit в командной строке  
  
-   Включить [дополнительные](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) параметр компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Option Explicit` инструкцию, чтобы обеспечить явное объявление всех переменных. Попытка использования необъявленных переменных приводит к ошибке во время компиляции.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>См. также

- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
