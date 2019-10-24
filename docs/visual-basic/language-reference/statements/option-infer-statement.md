---
title: Оператор Option Infer (Visual Basic)
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
ms.openlocfilehash: 4dcca0f0ed9989577ded27bab7cf3b16f3036964
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775457"
---
# <a name="option-infer-statement"></a>Option Infer - оператор

Включает использование локального определения типов при объявлении переменных.

## <a name="syntax"></a>Синтаксис

```vb
Option Infer { On | Off }
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`On`|Необязательный. Включает локальное определение типов.|
|`Off`|Необязательный. Отключает локальное определение типов.|

## <a name="remarks"></a>Заметки

Чтобы задать `Option Infer` в файле, введите `Option Infer On` или `Option Infer Off` в начале файла перед всем остальным исходным кодом. Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.

Если задать для `Option Infer` значение `On`, можно объявлять локальные переменные, не задавая явным образом тип данных. Компилятор определяет тип переменной по типу ее выражения инициализации.

На следующей иллюстрации `Option Infer` включен. Переменная в объявлении `Dim someVar = 2` объявляется как целочисленная определением типов.

На следующем снимке экрана показан IntelliSense при включенном параметре Infer:

![Снимок экрана, показывающий представление IntelliSense при включенном параметре Infer.](./media/option-infer-statement/option-infer-as-integer-on.png)

На следующей иллюстрации `Option Infer` отключен. Переменная в объявлении `Dim someVar = 2` объявляется как `Object` определением типов. В этом **примере на** [странице Компиляция в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)установлено значение **выкл** .

На следующем снимке экрана показан IntelliSense при отключенном параметре Infer:

![Снимок экрана, показывающий представление IntelliSense при отключенном параметре Infer.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> Если переменная объявлена как `Object`, тип времени выполнения может измениться в ходе работы программы. Visual Basic выполняет операции, называемые *упаковкой* *и распаковкой, для преобразования* между `Object` и типом значения, что делает выполнение более медленным. Дополнительные сведения о упаковке и распаковке см. в разделе [Спецификация языка Visual Basic](~/_vblang/spec/conversions.md#value-type-conversions).

Определение типов применяется на уровне процедур и не применяется вне процедур в классах, структурах, модулях и интерфейсах.

Дополнительные сведения см. в разделе [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

## <a name="when-an-option-infer-statement-is-not-present"></a>Если оператор Option Infer отсутствует

Если исходный код не содержит инструкцию `Option Infer`, то используется параметр **Option Infer** на [странице Компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Если используется компилятор командной строки, используется параметр компилятора [-оптионинфер](../../../visual-basic/reference/command-line-compiler/optioninfer.md) .

#### <a name="to-set-option-infer-in-the-ide"></a>Чтобы включить Option Infer в среде разработки

1. Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.

2. Откройте вкладку **Компиляция**.

3. Задайте значение в поле **параметр Infer** .

При создании нового проекта параметр **Option Infer** на вкладке **Компиляция** имеет значение **Option Infer** в диалоговом окне настройки **VB по умолчанию** . Чтобы открыть диалоговое окно **настройки VB по умолчанию** , в меню **Сервис** выберите пункт **Параметры**. В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**. Начальным параметром по умолчанию в **VB по умолчанию** является `On`.

#### <a name="to-set-option-infer-on-the-command-line"></a>Чтобы включить Option Infer в командной строке

Включите параметр компилятора [-оптионинфер](../../../visual-basic/reference/command-line-compiler/optioninfer.md) в команду **vbc** .

## <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию

В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.

|Указан тип данных?|Указан инициализатор?|Пример|Результат|
|---|---|---|---|
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, возникает ошибка времени при компиляции.|
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. См. раздел [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, возникает ошибка времени компиляции.|
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|

## <a name="example"></a>Пример

В следующих примерах показано, как оператор `Option Infer` включает локальное определение типов.

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a>Пример

В следующем примере показано, что тип времени выполнения может различаться, когда переменная указана как `Object`.

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a>См. также

- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
