---
title: Как выполнить Создание новой переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: db317b160a27c7e38bddba82eb4eac3088886705
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506892"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Как выполнить Создание новой переменной (Visual Basic)
Создайте переменную с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>Создание новой переменной  
  
1.  Объявить эту переменную в `Dim` инструкции.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  Включают спецификации для переменной характеристики, такие как [частного](../../../../visual-basic/language-reference/modifiers/private.md), [статический](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Дополнительные сведения см. в разделе [характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Нет необходимости `Dim` ключевое слово, если вы используете другие ключевые слова в объявлении.  
  
3.  За спецификацией имя переменной, должно соответствовать Visual Basic правила и соглашения. Дополнительные сведения см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  После имени [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение, чтобы указать тип данных переменной.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Если вы не укажете тип данных, используется значение по умолчанию: `Object`.  
  
5.  Выполните `As` предложение со знака равенства (`=`) и следовать знак равенства с начальным значением переменной.  
  
     Visual Basic назначает указанное значение переменной, каждый раз при его запуске `Dim` инструкции. Если начальное значение не задано, Visual Basic назначает начальное значение по умолчанию для типа данных переменной, при первом выполнении кода, содержащего `Dim` инструкции.  
  
     Если переменная является ссылочным типом, можно создать экземпляр своего класса, включая [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово в `As` предложение. Если вы не используете `New`, начальное значение переменной равно [ничего не](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
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
