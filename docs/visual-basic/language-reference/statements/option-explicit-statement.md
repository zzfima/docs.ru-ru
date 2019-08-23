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
ms.openlocfilehash: c027964d185d7f69c0a56a4386bedc2d8f9d2eac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912339"
---
# <a name="option-explicit-statement-visual-basic"></a>Оператор Option Explicit (Visual Basic)
Заставляет явно объявлять все переменные в файле или допускает неявные объявления переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Части  
 `On`  
 Необязательный параметр. Включает `Option Explicit` проверку. Если `On` параметр `Off` или не указан, по умолчанию `On`используется значение.  
  
 `Off`  
 Необязательный параметр. Отключает `Option Explicit` проверку.  
  
## <a name="remarks"></a>Примечания  
 Если `Option Explicit On` `Dim` `ReDim` или `Option Explicit` присутствует в файле, необходимо явно объявить все переменные с помощью инструкций или. При попытке использовать необъявленное имя переменной во время компиляции возникает ошибка. `Option Explicit Off` Оператор допускает неявное объявление переменных.  
  
 Если используется оператор `Option Explicit`, он должен быть указан в файле до всех прочих операторов.  
  
> [!NOTE]
> Установка `Option Explicit` в`Off` обычно не является хорошей практикой. Вы можете допустить ошибку при вводе имени переменной в одном или нескольких местах, что приведет к непредвиденным результатам при выполнении программы.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Если отсутствует оператор Option Explicit  
 Если исходный код не содержит `Option Explicit` инструкцию, то используется **параметр Explicit** на [странице Компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Если используется компилятор командной строки, используется параметр компилятора [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) .  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Установка параметра Explicit в интегрированной среде разработки  
  
1. Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Откройте вкладку **Компиляция**.  
  
3. Задайте значение в явном поле **Option** .  
  
 При создании нового проекта параметр **Option Explicit** на вкладке **Компиляция** имеет значение **Option Explicit** в диалоговом окне Параметры **VB по умолчанию** . Чтобы открыть диалоговое окно **настройки VB по умолчанию** , в меню **Сервис** выберите пункт **Параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальным значением по умолчанию в `On` **VB по умолчанию** является.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Установка параметра Explicit в командной строке  
  
- Включите параметр компилятора [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) в команду **vbc** .  
  
## <a name="example"></a>Пример  
 В следующем примере `Option Explicit` оператор используется для принудительного явного объявления всех переменных. Попытка использовать необъявленную переменную вызывает ошибку во время компиляции.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>См. также

- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
