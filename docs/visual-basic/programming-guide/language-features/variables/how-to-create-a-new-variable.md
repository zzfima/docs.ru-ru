---
title: Практическое руководство. Создание новой переменной (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aff160584d3d1fe382020d5b8c25ac57dab66d92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Практическое руководство. Создание новой переменной (Visual Basic)
Создайте переменную с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>Создание новой переменной  
  
1.  Объявите переменную в `Dim` инструкции.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  Включать спецификации для переменной характеристики, такие как [закрытый](../../../../visual-basic/language-reference/modifiers/private.md), [статических](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Дополнительные сведения см. в разделе [характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Нет необходимости `Dim` ключевое слово, при использовании других ключевых слов в объявлении.  
  
3.  За спецификацией имя переменной, которой необходимо следовать Visual Basic правила и соглашения. Дополнительные сведения см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  После имени [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложений, чтобы указать тип данных переменной.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Если тип данных не указан, используется значение по умолчанию: `Object`.  
  
5.  Выполните `As` предложение со знака равенства (`=`) и за ним начальное значение переменной.  
  
     Visual Basic присваивает указанное значение переменной при каждом запуске `Dim` инструкции. Если начальное значение не задано, Visual Basic назначает начальное значение по умолчанию для типа данных переменной при первом выполнении кода, содержащего `Dim` инструкции.  
  
     Если переменная является ссылочным типом, можно создать экземпляр класса, включая [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово в `As` предложения. Если вы не используете `New`, начальное значение переменной равно [ничего не](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>См. также  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
