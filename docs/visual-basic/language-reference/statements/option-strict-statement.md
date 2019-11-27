---
title: Option Strict Statement
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
ms.openlocfilehash: a002526a107fdc6e8e02890d11db94a3d224c94b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353763"
---
# <a name="option-strict-statement"></a>Option Strict Statement
Ограничивают неявные преобразования типов данных только расширяющими преобразованиями, запрещает позднее связывание и запрещает неявную типизацию, которая приводит к типу `Object`.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`On`|Необязательный элемент. Включает проверку `Option Strict`.|  
|`Off`|Необязательный элемент. Отключает проверку `Option Strict`.|  
  
## <a name="remarks"></a>Примечания  
 При появлении `Option Strict On` или `Option Strict` в файле следующие условия приводят к ошибке времени компиляции:  
  
- неявные сужающие преобразования;  
  
- Позднее связывание  
  
- неявная типизация, которая приводит к типу `Object`.  
  
> [!NOTE]
> В конфигурациях предупреждений, которые можно установить на [странице Компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), существует три параметра, которые соответствуют трем условиям, вызывающим ошибку во время компиляции. Сведения об использовании этих параметров см. в разделе [Настройка конфигураций предупреждений в интегрированной среде разработки](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) далее в этой статье.  
  
 Инструкция `Option Strict Off` отключает проверку ошибок и предупреждений для всех трех условий, даже если связанные параметры интегрированной среды разработки указывают на включение этих ошибок или предупреждений. Инструкция `Option Strict On` включает проверку ошибок и предупреждений для всех трех условий, даже если связанные параметры интегрированной среды разработки указывают на отключение этих ошибок или предупреждений.  
  
 При использовании оператор `Option Strict` должен находиться перед любыми другими инструкциями кода в файле.  
  
 Если для `Option Strict` задано значение `On`, Visual Basic проверяет, указаны ли типы данных для всех элементов программирования. Типы данных могут быть заданы явно или заданы с помощью определения локального типа. Указание типов данных для всех элементов программирования рекомендуется по следующим причинам.  
  
- Он обеспечивает поддержку IntelliSense для переменных и параметров. Это позволяет видеть их свойства и другие члены при вводе кода.  
  
- Он позволяет компилятору выполнять проверку типов. Проверка типов помогает найти инструкции, которые могут завершиться ошибкой во время выполнения из-за ошибок преобразования типов. Он также определяет вызовы методов для объектов, которые не поддерживают эти методы.  
  
- Это ускоряет выполнение кода. Одна из причин этого заключается в том, что если не указать тип данных для программного элемента, компилятор Visual Basic присваивает ему тип `Object`. Скомпилированному коду может потребоваться выполнить преобразование между `Object` и другими типами данных, что снижает производительность.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Неявные узкие ошибки преобразования  
 Ошибки неявных сужающих преобразований возникают при наличии неявного преобразования типа данных, которое является сужающим преобразованием.  
  
 Visual Basic может преобразовывать многие типы данных в другие типы данных. Потери данных могут происходить, когда значение одного типа данных преобразуется в тип данных с меньшей точностью или меньшей емкостью. Ошибка времени выполнения возникает в случае сбоя такого преобразования с сужением. `Option Strict` обеспечивает уведомление во время компиляции об этих сужающих преобразованиях, чтобы их можно было избежать. Дополнительные сведения см. в разделе [явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) , а [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Преобразования, которые могут вызвать ошибки, включают неявные преобразования, происходящие в выражениях. Дополнительные сведения см. в следующих разделах:  
  
- [Оператор +](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
- [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
- [Оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
- [Оператор/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
- [Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 При сцеплении строк с помощью [оператора &](../../../visual-basic/language-reference/operators/concatenation-operator.md)все преобразования в строки считаются расширяющими. Поэтому эти преобразования не создают неявные сужающие ошибки преобразования, даже если `Option Strict` имеет значение ON.  
  
 При вызове метода с аргументом, который имеет тип данных, отличный от соответствующего параметра, понижающие преобразования вызывают ошибку времени компиляции, если `Option Strict` имеет значение ON. Ошибку времени компиляции можно избежать, используя расширяющее преобразование или явное преобразование.  
  
 Неявные сужающие ошибки преобразования подавляются во время компиляции для преобразования из элементов коллекции `For Each…Next` в переменную управления циклом. Это происходит, даже если `Option Strict` включен. Дополнительные сведения см. в подразделе «сужающие преобразования» раздела [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Ошибки позднего связывания  
 Позднее связывание объекта возникает при его присваивании свойству или методу переменной, объявленной с типом `Object`. Дополнительные сведения см. в разделе [раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Ошибки неявного типа объекта  
 Ошибки неявных типов объектов возникают, когда для объявленной переменной невозможно вывести соответствующий тип, поэтому выводится тип `Object`. Это происходит в основном при использовании оператора `Dim` для объявления переменной без использования предложения `As`, если параметр `Option Infer` отключен. Дополнительные сведения см. в разделе [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) и [Спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
 Для параметров метода предложение `As` является необязательным, если `Option Strict` имеет значение OFF. Однако если какой либо параметр использует предложение `As`, все они должны использовать его. Если `Option Strict` имеет значение ON, для каждого определения параметра требуется предложение `As`.  
  
 Если переменная объявляется без использования предложения `As` и для нее задано значение `Nothing`, переменная имеет тип `Object`. В этом случае ошибка времени компиляции не возникает, если `Option Strict` включен и `Option Infer` находится в on. Примером этого является `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию  
 В следующей таблице описаны результаты различных сочетаний с указанием типа данных и инициализатора в [операторе Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, возникает ошибка времени при компиляции.|  
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. См. раздел [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, возникает ошибка времени компиляции.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Если отсутствует оператор Option Case  
 Если исходный код не содержит инструкцию `Option Strict`, то используется **параметр Option ограничивал** на [странице Компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . На **странице Компиляция** имеются параметры, обеспечивающие дополнительный контроль над условиями, которые вызывают ошибку.  
  
 При использовании компилятора командной строки можно использовать параметр компилятора [-оптионстрикт](../../../visual-basic/reference/command-line-compiler/optionstrict.md) , чтобы указать параметр для `Option Strict`.  
  
### <a name="to-set-option-strict-in-the-ide"></a>Установка Option в интегрированной среде разработки  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1. Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. На вкладке **Компиляция** задайте значение в поле **optioned (параметр)** .  
  
### <a name="conditions"></a>Установка конфигураций предупреждений в интегрированной среде разработки  
 При использовании [страницы компиляции конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) , а не инструкция `Option Strict`, имеет дополнительный контроль над условиями, которые создают ошибки. Раздел **конфигурации предупреждений** на **странице Компиляция** имеет параметры, соответствующие трем условиям, вызывающим ошибку во время компиляции, когда `Option Strict` находится в состоянии on. Ниже приведены эти параметры.  
  
- **Неявное преобразование**  
  
- **Позднее связывание; возможный сбой вызова во время выполнения**  
  
- **Неявный тип; предполагается объект**  
  
 При задании для параметра **Option Strict** значения **Вкл** для всех трех параметров конфигурации предупреждений задается значение **Ошибка**. При задании для параметра **Option Strict** значения **Выкл** для всех трех параметров задается значение **Нет**.  
  
 Вы можете задать для каждого отдельного параметра конфигурации предупреждений значение **Нет**, **Предупреждение** или **Ошибка**. Если всем трем параметрам конфигурации предупреждений присвоено значение **Ошибка**, в поле `On` указывается значение `Option strict`. Если всем трем параметрам присвоено значение **Нет**, в этом поле указывается значение `Off`. Для любого другого сочетания этих параметров указывается значение **(пользовательский)** .  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Задание параметра установки по умолчанию для новых проектов  
 При создании проекта на вкладке **Компиляция** в параметре **Option** -Setting задано значение, установленное **в параметре** в диалоговом окне **Параметры** .  
  
 Чтобы задать `Option Strict` в этом диалоговом окне, в меню **Сервис** выберите пункт **Параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальным параметром по умолчанию в **VB по умолчанию** является `Off`.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Установка параметра Option в командной строке  
 Включите параметр компилятора [-оптионстрикт](../../../visual-basic/reference/command-line-compiler/optionstrict.md) в команду **vbc** .  
  
## <a name="example"></a>Пример  
 В следующих примерах показаны ошибки времени компиляции, вызванные неявными преобразованиями типов, которые являются сужающими преобразованиями. Эта категория ошибок соответствует условию **неявного преобразования** на **странице Компиляция**.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана ошибка времени компиляции, вызванная поздним связыванием. Эта категория ошибок соответствует **поздней привязке; вызов может завершиться сбоем во время выполнения** на **странице компиляции**.  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>Пример  
 В следующих примерах демонстрируются ошибки, вызванные переменными, объявленными с неявным типом `Object`. Эта категория ошибок соответствует **неявному типу; предполагаемое условие объекта** на **странице компиляции**.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>См. также

- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Страница "Компиляция" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Практическое руководство. Доступ к членам объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Позднее связывание в решениях Office](/visualstudio/vsto/late-binding-in-office-solutions)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
