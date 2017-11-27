---
title: Option Strict Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "49"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 238f64001b097b86306e0ed9630bd5df2e6a189f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="option-strict-statement"></a>Option Strict Statement
Ограничивает неявное преобразование типов данных только до расширяющегося преобразования, не разрешает позднее связывание и неявную типизацию, в результате `Object` типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`On`|Необязательно. Позволяет `Option Strict` проверки.|  
|`Off`|Необязательно. Отключает `Option Strict` проверки.|  
  
## <a name="remarks"></a>Примечания  
 Когда `Option Strict On` или `Option Strict` появится в файле следующих условий вызывают ошибку компиляции:  
  
-   Неявные сужающие преобразования  
  
-   Позднее связывание  
  
-   Неявное типизирование, в результате `Object` типа  
  
> [!NOTE]
>  В конфигурации предупреждений, которые могут быть установлены для [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), существует три параметра, которые соответствуют три условия, которые вызывают ошибку компиляции. Сведения об использовании этих параметров см. в разделе [Задание конфигурации предупреждений в Интегрированной среде разработки](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) далее в этом разделе.  
  
 `Option Strict Off` Инструкция отключает ошибки и предупреждения проверки для всех трех условий, даже если указать соответствующие параметры интегрированной среды разработки для включения этих ошибок или предупреждений. `Option Strict On` Инструкция включает ошибки и предупреждения проверки для всех трех условий, даже если указать соответствующие параметры интегрированной среды разработки для отключения этих ошибок или предупреждений.  
  
 При использовании `Option Strict` оператор должен находиться перед всеми остальными операторами кода в файле.  
  
 При задании `Option Strict` для `On`, Visual Basic проверяет, что типы данных определяются для всех элементов программирования. Типы данных могут быть определены явным образом или с помощью локального определения типов. Указание типов данных для всех элементов программирования рекомендуется по следующим причинам:  
  
-   Она включает поддержку IntelliSense для переменных и параметров. Это дает возможность видеть их свойства и другие члены, при вводе кода.  
  
-   Это позволяет компилятору выполнять проверку типов. Проверка типа помогает найти инструкции, которые могут вызвать сбой во время выполнения из-за ошибки преобразования типов. Он также определяет вызовы методов в объектах, которые не поддерживают эти методы.  
  
-   Это увеличивает скорость выполнения кода. Один причина этого заключается в том, что если не указать тип данных для элемента программирования, компилятор Visual Basic присваивает его `Object` типа. Скомпилированный код может потребоваться преобразовать и переключений между `Object` и других типов данных, что снижает производительность.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Неявные сужающие преобразования ошибок  
 Неявные сужающие преобразования происходят при неявном преобразовании типов данных, является сужающим преобразованием.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]можно преобразовать многих типов данных в другие типы данных. Когда значение одного типа данных преобразуется в тип данных с меньшей точностью или меньшей емкостью может произойти потеря данных. Ошибка во время выполнения возникает, если сужающее преобразование завершается сбоем. `Option Strict`обеспечивает уведомление во время компиляции сужающего преобразования, чтобы можно было избежать их. Дополнительные сведения см. в разделе [неявные и явные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) и [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Преобразования, которые могут привести к ошибкам входят неявные преобразования, возникающие в выражениях. Дополнительные сведения см. в следующих разделах:  
  
-   [Оператор +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 При объединении строк с помощью [& оператор](../../../visual-basic/language-reference/operators/concatenation-operator.md), расширяющими считаются все преобразования на строки. Поэтому эти преобразования не создает неявные сужающие преобразования ошибки, даже если `Option Strict` включен.  
  
 При вызове метода, который имеет тип данных отличается от соответствующего параметра в качестве аргумента, сужающее преобразование приводит к ошибке во время компиляции, если `Option Strict` включен. Ошибка времени компиляции можно избежать с помощью расширяющего преобразования или явное преобразование.  
  
 Неявные сужающие ошибок преобразования отключено во время компиляции для преобразования из элементов в `For Each…Next` коллекции для управляющей переменной цикла. Это происходит, даже если `Option Strict` включен. Дополнительные сведения см. в подразделе «Сужающие преобразования» [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Позднее связывание, ошибки  
 Объект позднего связывания, когда он присваивается свойству или методу объекта переменной, объявленной с типом `Object`. Дополнительные сведения см. в разделе [раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Тип ошибки неявных объектов  
 Появление сообщений типа неявных объектов соответствующего типа не может быть выведен для объявленной переменной, поэтому тип `Object` выводится. Это в первую очередь происходит при использовании `Dim` инструкции для объявления переменной без использования `As` предложения, и `Option Infer` отключен. Дополнительные сведения см. в разделе [Option Infer-оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Параметры метода `As` предложении является обязательным, если `Option Strict` отключен. Тем не менее если любой из параметров использует `As` предложения, все они должны использовать его. Если `Option Strict` , `As` предложение является обязательным для каждого определения параметра.  
  
 Если переменная объявлена без использования `As` предложения и присвойте ему значение `Nothing`, переменная имеет тип `Object`. В этом случае возникает ошибка во время компиляции не при `Option Strict` включен и `Option Infer` включен. Примером этого является `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию  
 В следующей таблице описаны результаты различных сочетаний заданных типов данных и инициализаторов в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Если оператор Option Strict отсутствует  
 Если исходный код не содержит `Option Strict` инструкции **Option strict** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. **Компиляция** имеет параметры, которые обеспечивают дополнительный контроль над условия, которые вызывают ошибку.  
  
 При использовании компилятора командной строки можно использовать [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) указано значение для параметра компилятора `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Чтобы задать Option Strict в Интегрированной среде разработки  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  На **компиляции** вкладку, задайте значение **Option Strict** поле.  
  
###  <a name="conditions"></a>Задание конфигурации предупреждений в Интегрированной среде разработки  
 При использовании [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) вместо `Option Strict` инструкции, у вас есть дополнительный контроль над условия, которые приводят к ошибкам. **Конфигурации предупреждений** раздел **компиляция** имеет параметры, которые соответствуют три условия, которые вызывают ошибку компиляции при `Option Strict` включен. Ниже приведены эти параметры.  
  
-   **Неявное преобразование**  
  
-   **Позднее связывание; может произойти сбой вызова во время выполнения**  
  
-   **Неявный тип; предполагается, что объект**  
  
 При задании **Option Strict** для **на**, все три из этих параметров конфигурации предупреждение присваиваются **ошибка**. При задании **Option Strict** для **Off**, заданы все три параметра, **нет**.  
  
 Можно изменить по отдельности каждой конфигурации предупреждение, установите значение **нет**, **предупреждение**, или **ошибка**. Если все три предупреждение параметры конфигурации заданы для **ошибка**, `On` отображается в `Option strict` поле. Если все три **нет**, `Off` отображается в этом поле. Для любого сочетания этих параметров **(пользовательский)** отображается.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Чтобы задать параметр Option Strict по умолчанию для новых проектов  
 При создании проекта, **Option Strict** на **компиляции** набор вкладок **Option Strict** в **параметры** диалоговое окно.  
  
 Чтобы задать `Option Strict` в этом диалоговом на **средства** меню, нажмите кнопку **параметры**. В **параметры** диалогового окна разверните **проекты и решения**, а затем нажмите кнопку **VB по умолчанию**. Начальный параметр по умолчанию в **VB значения по умолчанию** — `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Чтобы задать параметр Option Strict в командной строке  
 Включить [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметра компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируется ошибки времени компиляции, вызванные неявного преобразования типов, сужающие преобразования. Соответствует этой категории ошибок **неявное преобразование** условия на **компиляция**.  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано ошибка времени компиляции, вызванные позднего связывания. Соответствует этой категории ошибок **Late связывание; возможный сбой вызова во время выполнения** условия на **компиляция**.  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируется ошибки, вызванные переменные, объявленные с типом неявное `Object`. Соответствует этой категории ошибок **явного типа; предполагается, что объект** условия на **компиляция**.  
  
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
