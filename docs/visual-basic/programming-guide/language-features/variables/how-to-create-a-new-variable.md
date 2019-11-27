---
title: Практическое руководство. Создание новой переменной
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 2a2b5b8bef3b66f9727f0e65b61882186c007e94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353636"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Практическое руководство. Создание новой переменной (Visual Basic)

Переменная создается с помощью [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>Создание новой переменной

1. Объявите переменную в операторе `Dim`.

    ```vb
    Dim newCustomer
    ```

2. Включите спецификации для характеристик переменной, например [Private](../../../../visual-basic/language-reference/modifiers/private.md), [static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Дополнительные сведения см. в разделе [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    Ключевое слово `Dim` не требуется, если в объявлении используются другие ключевые слова.

3. Используйте спецификации с именем переменной, которое должно соответствовать правилам и соглашениям Visual Basic. Дополнительные сведения см. в разделе [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Чтобы указать тип данных переменной, используйте имя с предложением [as](../../../../visual-basic/language-reference/statements/as-clause.md) .

    ```vb
    Public Static newCustomer As Customer
    ```

    Если тип данных не указан, используется значение по умолчанию: `Object`.

5. Следуйте предложению `As` со знаком равенства (`=`) и выполните знак равенства с начальным значением переменной.

    Visual Basic назначает указанное значение переменной при каждом выполнении инструкции `Dim`. Если не указать начальное значение, Visual Basic присваивает начальное значение по умолчанию для типа данных переменной при первом входе в код, содержащий инструкцию `Dim`.

    Если переменная является ссылочным типом, можно создать экземпляр его класса, включив в предложение `As` новое ключевое слово [operator](../../../../visual-basic/language-reference/operators/new-operator.md) . Если `New`не используется, начальным значением переменной будет [Nothing](../../../../visual-basic/language-reference/nothing.md).

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>См. также

- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Операторы](../../../../visual-basic/language-reference/statements/index.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
