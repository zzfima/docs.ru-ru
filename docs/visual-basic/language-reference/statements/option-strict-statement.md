---
title: Option Strict Statement (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: ac8f6fa2ebd2f8d846c3662184c83a83477e2311
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659265"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Ограничивает неявное преобразование типов данных расширяющими преобразованиями, запрещает позднее связывание и неявную типизацию, которые приводят к `Object` типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`On`|Необязательный. Позволяет `Option Strict` проверки.|  
|`Off`|Необязательный. Отключает `Option Strict` проверки.|  
  
## <a name="remarks"></a>Примечания  
 Когда `Option Strict On` или `Option Strict` появится в файле, следующие условия вызывают ошибку времени компиляции:  
  
-   неявные сужающие преобразования;  
  
-   Позднее связывание  
  
-   неявная типизация, которая приводит к типу `Object`.  
  
> [!NOTE]
>  В конфигурации предупреждений, которые можно установить на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), существует три параметра, которые соответствуют три условия, которые вызывают ошибку времени компиляции. Сведения о том, как с помощью этих параметров см. в разделе [для задания конфигурации предупреждений в интегрированной среде разработки](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) далее в этом разделе.  
  
 `Option Strict Off` Инструкция отключает ошибки и предупреждения проверки для всех трех условий, даже если указать соответствующие параметры интегрированной среды разработки для включения этих ошибок или предупреждений. `Option Strict On` Инструкция включает ошибки и предупреждения проверки для всех трех условий, даже если указать соответствующие параметры интегрированной среды разработки для отключения этих ошибок или предупреждений.  
  
 При использовании `Option Strict` оператор должен находиться перед всеми остальными операторами код в файле.  
  
 При задании `Option Strict` для `On`, Visual Basic проверяет, что типы данных указаны для всех элементов программирования. Типы данных может быть задан явным образом или с помощью вывод локального типа. Задание типов данных для всех элементов программирования рекомендуется по следующим причинам:  
  
-   Она включает поддержку IntelliSense для переменных и параметров. Это позволяет видеть их свойства и другие члены, при вводе кода.  
  
-   Он позволяет компилятору выполнять проверку типов. Проверка типов помогает найти инструкции, которые могут вызвать сбой во время выполнения из-за ошибок преобразования типов. Она также определяет вызовы методов в объектах, которые не поддерживают эти методы.  
  
-   Она ускоряет выполнение кода. Один обусловлено тем, что если вы не укажете тип данных для элемента программирования, компилятор Visual Basic присваивает его `Object` типа. Скомпилированный код может потребоваться преобразование между `Object` и другие типы данных, что снижает производительность.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Ошибки неявных сужающих преобразований  
 Ошибки неявных сужающих преобразований возникают при наличии неявного преобразования типа данных, которое является сужающим преобразованием.  
  
 Visual Basic можно преобразовать множество типов данных в другие типы данных. Если значение одного типа данных преобразуется в тип данных с меньшей точностью или меньшей емкостью может произойти потеря данных. Ошибка времени выполнения возникает при сбое сужающего преобразования. `Option Strict` обеспечивает уведомление во время компиляции об этих сужающие преобразования, таким образом, чтобы их можно избежать. Дополнительные сведения см. в разделе [явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) и [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Преобразования, которые могут привести к ошибкам включаются неявные преобразования, возникающие в выражениях. Дополнительные сведения см. в следующих разделах:  
  
-   [Оператор +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 Когда вы можете сцеплять строки с помощью [& оператор](../../../visual-basic/language-reference/operators/concatenation-operator.md), расширяющимся учитываются все преобразования в строки. Поэтому эти преобразования не создают неявные сужающие преобразования возникла ошибка, даже если `Option Strict` включен.  
  
 При вызове метода, имеющего аргумент с типом данных отличается от соответствующего параметра, сужающее преобразование приводит к ошибке времени компиляции, если `Option Strict` включен. Ошибка времени компиляции можно избежать с помощью расширяющего преобразования или явное преобразование.  
  
 Ошибки неявных сужающих преобразований, подавляются во время компиляции для преобразования из элементов в `For Each…Next` коллекции для управляющей переменной цикла. Это происходит, даже если `Option Strict` включен. Дополнительные сведения см. в разделе «Сужающие преобразования» в [для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Позднее связывание ошибки  
 Позднее связывание объекта возникает при его присваивании свойству или методу переменной, объявленной с типом `Object`. Дополнительные сведения см. в разделе [раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Ошибки неявных типов объектов  
 Ошибки неявных типов объектов возникают, когда для объявленной переменной невозможно вывести соответствующий тип, поэтому выводится тип `Object`. Это происходит в основном при использовании оператора `Dim` для объявления переменной без использования предложения `As`, если параметр `Option Infer` отключен. Дополнительные сведения см. в разделе [оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Параметры метода `As` предложение является необязательным при `Option Strict` отключен. Тем не менее если любой из параметров использует `As` предложение, они все должны использовать его. Если `Option Strict` , `As` предложение является обязательным для каждого определения параметра.  
  
 Если переменная объявлена без использования `As` предложение и присвойте ему значение `Nothing`, переменную с типом `Object`. В этом случае происходит ошибка времени компиляции не при `Option Strict` включен и `Option Infer` включен. Примером этого является `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию  
 В следующей таблице описаны результаты различных сочетаний заданных типов данных и инициализаторов в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. См. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Если оператор Option Strict отсутствует  
 Если исходный код не содержит `Option Strict` инструкции **Option strict** на [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. **Страница "Компиляция"** имеет параметры, которые обеспечивают дополнительный контроль над условия, которые вызывают ошибку.  
  
 Если вы используете компилятор командной строки, можно использовать [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md) задавать значение для параметра компилятора `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Чтобы включить режим Strict в интегрированной среде разработки  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2.  На **компиляции** вкладку, задайте значение в **Option Strict** поле.  
  
###  <a name="conditions"></a> Чтобы задать конфигурации предупреждений в интегрированной среде разработки  
 При использовании [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) вместо `Option Strict` инструкции, вы получите дополнительный контроль условиями, которые выдают сообщения об ошибках. **Конфигурации предупреждений** раздел **страница "Компиляция"** имеет параметры, которые соответствуют три условия, которые вызывают ошибку времени компиляции при `Option Strict` включен. Ниже приведены эти параметры.  
  
-   **Неявное преобразование**  
  
-   **Позднее связывание; возможный сбой вызова во время выполнения**  
  
-   **Неявный тип; предполагается объект**  
  
 При задании для параметра **Option Strict** значения **Вкл** для всех трех параметров конфигурации предупреждений задается значение **Ошибка**. При задании для параметра **Option Strict** значения **Выкл** для всех трех параметров задается значение **Нет**.  
  
 Вы можете задать для каждого отдельного параметра конфигурации предупреждений значение **Нет**, **Предупреждение** или **Ошибка**. Если всем трем параметрам конфигурации предупреждений присвоено значение **Ошибка**, в поле `Option strict` указывается значение `On`. Если всем трем параметрам присвоено значение **Нет**, в этом поле указывается значение `Off`. Для любого другого сочетания этих параметров указывается значение **(пользовательский)**.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Чтобы задать параметр Option Strict по умолчанию для новых проектов  
 При создании проекта, **Option Strict** на **компиляции** набор вкладок **Option Strict** в **параметры** диалоговое окно.  
  
 Чтобы задать `Option Strict` в этом диалоговом окне на **средства** меню, щелкните **параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальная настройка по умолчанию в **параметры Visualbasic по умолчанию** является `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Чтобы включить режим Strict в командной строке  
 Включить [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируется ошибки времени компиляции, из-за неявного преобразования типов, которые являются сужающими преобразованиями. Соответствует этой категории ошибок **неявное преобразование** условие на **страница "Компиляция"**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано ошибку времени компиляции, из-за позднего связывания. Соответствует этой категории ошибок **Late связывание; возможный сбой вызова во время выполнения** условие на **страница "Компиляция"**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируется ошибки, вызванные переменные, объявленные с типом неявное `Object`. Соответствует этой категории ошибок **неявный тип; предполагается объект** условие на **страница "Компиляция"**.  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Практическое руководство. Доступ к членам объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Позднее связывание в решениях Office](https://msdn.microsoft.com/library/3xxe951d)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
