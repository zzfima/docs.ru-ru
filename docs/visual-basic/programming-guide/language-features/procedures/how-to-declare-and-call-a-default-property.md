---
title: "Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: ce98e7fe72a395f6c4cde481feaa60be28c6fcc3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic
Объект *по умолчанию свойство* является свойством класса или структуры, созданный код имеет доступ без его указания. Если вызывающий код задает класс или структуру, но не со свойством, а контекст разрешает доступ к свойству [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] разрешает доступ к этого класса или структуры свойство по умолчанию, если он существует.  
  
 Класс или структура может иметь не более одного свойства по умолчанию. Тем не менее можно перегружать свойство по умолчанию и иметь более одной версии.  
  
 Дополнительные сведения см. в разделе [по умолчанию](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Для объявления свойства по умолчанию  
  
1.  Объявите свойство обычным способом. Не указывайте `Shared` или `Private` ключевое слово.  
  
2.  Включить `Default` ключевое слово в объявлении свойства.  
  
3.  Укажите хотя бы один параметр свойства. Нельзя определить свойство по умолчанию, которая не принимает хотя бы один аргумент.  
  
     [!code-vb[VbVbcnProcedures&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Для вызова свойства по умолчанию  
  
1.  Объявите переменную типа содержащего класса или структуры.  
  
     [!code-vb[VbVbcnProcedures №&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Используйте имя переменной отдельно в выражении, где вы обычно содержит имя свойства.  
  
     [!code-vb[VbVbcnProcedures&#21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  После имени переменной список аргументов в скобках. Свойство по умолчанию должна принимать хотя бы один аргумент.  
  
     [!code-vb[VbVbcnProcedures&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Чтобы получить значение свойства по умолчанию, используйте имя переменной со списком аргументов в выражении или после равенства (`=`) входа в операторе присваивания.  
  
     [!code-vb[VbVbcnProcedures&#15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Чтобы задать значение свойства по умолчанию, используйте имя переменной со списком аргументов слева от оператора присваивания.  
  
     [!code-vb[VbVbcnProcedures&#14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Всегда можно указать имя свойства по умолчанию вместе с именем переменной, так же, как это делается для доступа к любым другим свойством.  
  
     [!code-vb[VbVbcnProcedures&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется свойство по умолчанию для класса.  
  
 [!code-vb[VbVbcnProcedures&#12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует вызов свойства по умолчанию `myProperty` класса `class1`. Три оператора присваивания сохраняют значения в `myProperty`и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>вызов считывает значения.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
 [!code-vb[VbVbcnProcedures&#13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 Наиболее распространенное использование свойства по умолчанию является <xref:Microsoft.VisualBasic.Collection.Item%2A>Свойства для различных классов коллекций.</xref:Microsoft.VisualBasic.Collection.Item%2A>  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Свойства по умолчанию может привести к небольшому сокращению знаки исходного кода, но они могут сделать ваш код более сложным для чтения. Если вызывающий код не знаком с классом или структурой, когда он ссылается на имя класса или структуры, ее нельзя быть уверенным ли эта ссылка обращается к классу или структуре или свойство по умолчанию. Это может привести к ошибкам компилятора или ошибки слабая логики времени выполнения.  
  
 Можно частично уменьшить вероятность ошибок, связанных с свойство по умолчанию с помощью всегда [оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Чтобы задать тип проверки компилятором `On`.  
  
 Если вы планируете использовать предварительно определенный класс или структуру в коде, необходимо определить, имеет ли он свойство по умолчанию и если да, то, что ее имя —.  
  
 Из-за этих недостатков можно не определять свойства по умолчанию. Для удобства чтения кода следует также учитывать всегда ссылке на все свойства явным образом, даже свойства по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](./property-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [По умолчанию](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)   
 [Практическое руководство: создание свойства](./how-to-create-a-property.md)   
 [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md)   
 [Практическое руководство: поместить значение в свойстве](./how-to-put-a-value-in-a-property.md)   
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
