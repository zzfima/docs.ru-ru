---
title: "Практическое руководство: Создание новой переменной (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2856fe19ddc48a14385aaae7b1c331fcb96c0554
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Практическое руководство. Создание новой переменной (Visual Basic)
Создайте переменную с [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>Создание новой переменной  
  
1.  Объявите переменную в `Dim` инструкции.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  Включают спецификации для переменной характеристики, такие как [частного](../../../../visual-basic/language-reference/modifiers/private.md), [статических](../../../../visual-basic/language-reference/modifiers/static.md), [тени](../../../../visual-basic/language-reference/modifiers/shadows.md), или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Дополнительные сведения см. в разделе [характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Не требуется `Dim` ключевое слово, при использовании других ключевых слов в объявлении.  
  
3.  За спецификацией должно следовать имя переменной, которой должны следовать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] правила и соглашения. Дополнительные сведения см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  После имени [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение, чтобы указать тип данных переменной.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Если тип данных не указан, используется значение по умолчанию: `Object`.  
  
5.  Выполните `As` предложение со знака равенства (`=`) и за ним начальное значение переменной.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Присваивает указанное значение переменной при каждом запуске `Dim` инструкции. Если не указать начальное значение, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] назначает начальное значение по умолчанию для типа данных переменной при первом выполнении кода, содержащего `Dim` инструкции.  
  
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
 [Инструкции](../../../../visual-basic/language-reference/statements/index.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)

