---
title: "Option Strict оператор | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Strict
- vb.OptionStrict
dev_langs:
- VB
helpviewer_keywords:
- Strict keyword
- Option Strict statement
- conversions, implicit
- late binding
- implicit conversions
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 3bf0d4939f24c38392d7ca4764c41d12366067b5
ms.lasthandoff: 03/13/2017

---
# <a name="option-strict-statement"></a>Option Strict Statement
Ограничивает неявное преобразование типов данных расширяющими преобразованиями, запрещает позднее связывание и неявную типизацию, в результате `Object` типа.  
  
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
 Когда `Option Strict On` или `Option Strict` появится в файле следующие условия вызывают ошибку компиляции:  
  
-   Неявные сужающие преобразования  
  
-   Позднее связывание  
  
-   Неявное типизирование, в результате `Object` типа  
  
> [!NOTE]
>  В конфигурации предупреждений, которые могут быть установлены на [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), три параметра, которые соответствуют три условия, которые вызывают ошибку компиляции. Сведения об использовании этих параметров см. в разделе [Задание конфигурации предупреждений в Интегрированной среде разработки](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) далее в этом разделе.  
  
 `Option Strict Off` Инструкция отключает ошибки и предупреждения проверки для всех трех условий, даже если указать соответствующие параметры IDE для включения этих ошибок или предупреждений. `Option Strict On` Инструкция включает ошибки и предупреждения проверки для всех трех условий, даже если указать соответствующие параметры IDE для отключения этих ошибок или предупреждений.  
  
 При использовании `Option Strict` оператор должен находиться перед всеми остальными операторами кода в файле.  
  
 При задании `Option Strict` в `On`, Visual Basic проверяет, что типы данных определяются для всех элементов программирования. Типы данных могут быть определены явным образом или с помощью локального определения типов. Рекомендуется указывать типы данных для всех элементов программирования, по следующим причинам:  
  
-   Он обеспечивает поддержку IntelliSense для переменных и параметров. Это позволяет видеть их свойства и другие члены, при вводе кода.  
  
-   Это позволяет компилятору выполнять проверку типов. Проверка типа помогает найти инструкции, которые могут вызвать сбой во время выполнения из-за ошибки преобразования типа. Он также определяет вызовы методов для объектов, которые не поддерживают эти методы.  
  
-   Это значительно ускоряет выполнение кода. Одна причина этого заключается в том, что если не указать тип данных для элемента программирования, компилятор Visual Basic присваивает его `Object` типа. Скомпилированный код может потребоваться преобразовать вперед и назад между `Object` и других типов данных, что снижает производительность.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Неявные ошибки сужающие преобразования  
 Неявные сужающие преобразования ошибки встречаются при неявное преобразование типов данных, сужающего преобразования.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]можно преобразовать множество типов данных в другие типы данных. Когда значение одного типа данных преобразуется в тип данных с меньшей точностью или емкостью может произойти потеря данных. Ошибка во время выполнения возникает, если сужающее преобразование завершается неудачей. `Option Strict`обеспечивает во время компиляции уведомление об этих сужающих преобразованиях, чтобы можно было избежать их. Дополнительные сведения см. в разделе [неявных и явных преобразований](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) и [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Преобразования, которые могут привести к ошибкам относятся неявные преобразования, выполняемые в выражениях. Дополнительные сведения см. в следующих разделах:  
  
-   [Оператор +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [\ Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [/ =-Оператор (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 При объединении строк с помощью [& оператор](../../../visual-basic/language-reference/operators/concatenation-operator.md), расширяющими считаются все преобразования в строки. Поэтому неявное ошибка сужающего преобразования, даже если не создают эти преобразования `Option Strict` включен.  
  
 При вызове метода, который имеет тип данных отличается от соответствующего параметра в качестве аргумента, сужающее преобразование приводит к ошибке времени компиляции, если `Option Strict` включен. Ошибка времени компиляции можно избежать, используя расширяющее преобразование или явное преобразование.  
  
 Неявные ошибки сужающие преобразования подавляются во время компиляции для преобразования из элементов в `For Each…Next` коллекцию для переменной цикла. Это происходит, даже если `Option Strict` включен. Дополнительные сведения см. в разделе «Сужающие преобразования» [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Позднее связывание ошибки  
 Объект позднего связывания, когда она назначается свойство или метод, объявленный тип переменной `Object`. Дополнительные сведения см. в разделе [раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Ошибки неявного объект типа  
 Неявные объекта типа ошибки возникают, когда соответствующий тип не может быть выведен объявленной переменной, поэтому тип `Object` выводится. Это в первую очередь происходит при использовании `Dim` инструкции для объявления переменной без использования `As` предложение, и `Option Infer` отключен. Дополнительные сведения см. в разделе [Option Infer оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
 Параметры метода `As` является необязательным, если `Option Strict` отключен. Однако если любой из параметров использует `As` предложение, они все должны использовать его. Если `Option Strict` , `As` предложение является обязательным для каждого определения параметра.  
  
 Если переменная объявлена без использования `As` предложения и присвойте ему значение `Nothing`, переменная имеет тип `Object`. В этом случае возникает ошибка компиляции не при `Option Strict` включен и `Option Infer` включен. Примером этого является `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию  
 В следующей таблице описаны результаты различных сочетаний заданных типов данных и инициализаторов в [оператора Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператора Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Если оператор Option Strict не присутствует  
 Если исходный код не содержит `Option Strict` инструкции, **Option strict** на [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. **Компиляция** имеет параметры, которые обеспечивают дополнительный контроль над условия, которые вызывают ошибку.  
  
 Если вы используете компилятор командной строки, можно использовать [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметр компилятора для указания параметра `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Чтобы включить режим Strict в Интегрированной среде разработки  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
1.  В **обозревателе**, выберите проект. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  На **компиляции** , установите значение **Option Strict** поле.  
  
###  <a name="conditions"></a>Задание конфигурации предупреждений в Интегрированной среде разработки  
 При использовании [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) вместо `Option Strict` инструкции, Вы контролируете дополнительные условия, которые приводят к ошибкам. **Конфигурации предупреждений** раздел **компиляция** есть параметры, которые соответствуют три условия, которые вызывают ошибку компиляции при `Option Strict` включен. Ниже перечислены эти параметры.  
  
-   **Неявное преобразование**  
  
-   **Позднее связывание; возможный сбой вызова во время выполнения**  
  
-   **Неявный тип; предполагается объект**  
  
 При задании **Option Strict** для **на**, заданы все три эти параметры конфигурации предупреждение **ошибка**. При задании **Option Strict** для **отключение**, все три параметра равным **нет**.  
  
 Можно изменить по отдельности каждой предупреждение параметр конфигурации для **нет**, **предупреждение**, или **ошибка**. Если заданы все три параметры конфигурации предупреждение **ошибка**, `On` появляется в `Option strict` поле. Если все три **нет**, `Off` выводится в этом окне. Для любой комбинации этих параметров **(пользовательский)** отображается.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Чтобы задать параметр Option Strict по умолчанию для новых проектов  
 При создании проекта, **Option Strict** на **компиляции** задано значение **Option Strict** в **параметры** диалоговое окно.  
  
 Чтобы задать `Option Strict` в этом диалоговом на **средства** меню, щелкните **параметры**. В **параметры** диалогового окна разверните **проекты и решения**и нажмите кнопку **VB по умолчанию**. Начальный параметр по умолчанию в **VB значения по умолчанию** — `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Чтобы включить режим Strict в командной строке  
 Включить [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) параметра компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируется ошибки компиляции, вызванные неявного преобразования типов, являются сужающими. Эта категория ошибок соответствует **неявное преобразование** условие на **компиляция**.  
  
 [!code-vb[VbVbalrStatements&#161;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано ошибка времени компиляции, вызванные позднего связывания. Эта категория ошибок соответствует **Late связывание; возможный сбой вызова во время выполнения** условие на **компиляция**.  
  
 [!code-vb[VbVbalrStatements&#162;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируется ошибки, вызванные переменные, объявленные с типом неявное `Object`. Эта категория ошибок соответствует **неявный тип; предполагается объект** условие на **компиляция**.  
  
 [!code-vb[VbVbalrStatements&#163;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements&#164;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Практическое руководство: доступ к членам объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Позднее связывание в решениях Office](https://msdn.microsoft.com/library/3xxe951d)   
 [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
