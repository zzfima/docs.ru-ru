---
title: "Option Explicit-оператор (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 020f12f1fbb9a06647215f1fac6324e3b74e8a77
ms.lasthandoff: 03/13/2017

---
# <a name="option-explicit-statement-visual-basic"></a>Оператор Option Explicit (Visual Basic)
Вызывает принудительное явное объявление всех переменных в файле или допускает неявного объявления переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Части  
 `On`  
 Необязательный. Позволяет `Option Explicit` проверки. Если `On` или `Off` не указан, значение по умолчанию — `On`.  
  
 `Off`  
 Необязательный. Отключает `Option Explicit` проверки.  
  
## <a name="remarks"></a>Примечания  
 Когда `Option Explicit On` или `Option Explicit` появится в файле, необходимо явно объявить все переменные с помощью `Dim` или `ReDim` инструкции. При попытке использовать необъявленное имя переменной, происходит ошибка времени компиляции. `Option Explicit Off` Оператор разрешает неявное объявление переменных.  
  
 Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.  
  
> [!NOTE]
>  Установка `Option Explicit` для `Off` обычно не рекомендуется. Имя переменной в одно или несколько расположений, что может привести к непредвиденным результатам при выполнении программы может опечатка.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Если оператор Option Explicit не присутствует  
 Если исходный код не содержит `Option Explicit` инструкции, **Option Explicit** на [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. Если используется компилятор командной строки, [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) используется параметр компилятора.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Чтобы задать режим Explicit в Интегрированной среде разработки  
  
1.  В **обозревателе**, выберите проект. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Задайте значение в **Option Explicit** поле.  
  
 При создании нового проекта, **Option Explicit** на **компиляции** задано значение **Option Explicit** в **VB по умолчанию** диалоговое окно. Для доступа к **VB по умолчанию** в диалоговом **средства** меню, щелкните **параметры**. В **параметры** диалогового окна разверните **проекты и решения**и нажмите кнопку **VB по умолчанию**. Начальный параметр по умолчанию в **VB значения по умолчанию** — `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Чтобы задать режим Explicit в командной строке  
  
-   Включить [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) параметра компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Option Explicit` инструкции, чтобы обеспечить явное объявление всех переменных. Попытка использования необъявленных переменных приводит к ошибке во время компиляции.  
  
 [!code-vb[VbVbalrStatements&#47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements&#48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Дополнительные](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
