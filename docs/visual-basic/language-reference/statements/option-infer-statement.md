---
title: Option Infer Statement (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: f5c824df43997282d50c9c2a458fb1d854cc160a
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245795"
---
# <a name="option-infer-statement"></a>Option Infer - оператор
Включает использование локального определения типов при объявлении переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`On`|Необязательно. Включает локальное определение типов.|  
|`Off`|Необязательно. Отключает локальное определение типов.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы задать `Option Infer` в файле, введите `Option Infer On` или `Option Infer Off` в начале файла перед всем остальным исходным кодом. Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.  
  
 Если задать для `Option Infer` значение `On`, можно объявлять локальные переменные, не задавая явным образом тип данных. Компилятор определяет тип переменной по типу ее выражения инициализации.  
  
 На следующей иллюстрации `Option Infer` включен. Переменная в объявлении `Dim someVar = 2` объявляется как целочисленная определением типов.  
  
 ![IntelliSense-просмотров объявления. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")  
IntelliSense при включенном параметре Option Infer  
  
 На следующей иллюстрации `Option Infer` отключен. Переменная в объявлении `Dim someVar = 2` объявляется как `Object` определением типов. В этом примере **Option Strict** установлено значение **Off** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
 ![IntelliSense-просмотров объявления. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")  
IntelliSense при отключенном параметре Option Infer  
  
> [!NOTE]
>  Если переменная объявлена как `Object`, тип времени выполнения может измениться в ходе работы программы. Visual Basic выполняет операции *упаковки-преобразования* и *распаковки* для преобразования между `Object` и типом значения, что замедляет выполнение. Сведения об упаковке и распаковке см. в разделе [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).
  
 Определение типов применяется на уровне процедур и не применяется вне процедур в классах, структурах, модулях и интерфейсах.  
  
 Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="when-an-option-infer-statement-is-not-present"></a>Если оператор Option Infer отсутствует  
 Если исходный код не содержит `Option Infer` инструкции **Option Infer** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. Если используется компилятор командной строки, [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) используется параметр компилятора.  
  
#### <a name="to-set-option-infer-in-the-ide"></a>Чтобы включить Option Infer в среде разработки  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Задайте значение в **Option infer** поле.  
  
 При создании нового проекта, **Option Infer** на **компиляции** набор вкладок **Option Infer** в **Visual Basic по умолчанию** диалоговое окно. Чтобы получить доступ к **Visual Basic по умолчанию** диалоговом окне **средства** меню, щелкните **параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальная настройка по умолчанию в **параметры Visualbasic по умолчанию** является `On`.  
  
#### <a name="to-set-option-infer-on-the-command-line"></a>Чтобы включить Option Infer в командной строке  
  
-   Включить [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) параметр компилятора в **vbc** команды.  
  
## <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию  
 В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. См. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
## <a name="example"></a>Пример  
 В следующих примерах показано, как оператор `Option Infer` включает локальное определение типов.  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, что тип времени выполнения может различаться, когда переменная указана как `Object`.  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
