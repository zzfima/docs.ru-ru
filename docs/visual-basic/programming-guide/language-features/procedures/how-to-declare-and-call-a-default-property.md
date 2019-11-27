---
title: Инструкции. объявление и вызов свойства по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: b01188ed8a9ff4da95a6975dcac3509625fdffb2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349684"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic
*Свойство по умолчанию* — это свойство класса или структуры, к которому код может получить доступ без указания этого свойства. Если вызывающий код именует класс или структуру, но не свойство, и контекст разрешает доступ к свойству, Visual Basic разрешает доступ к свойству по умолчанию этого класса или структуры, если он существует.  
  
 Класс или структура может иметь не более одного свойства по умолчанию. Однако можно перегрузить свойство по умолчанию и иметь более одной версии.  
  
 Дополнительные сведения см. в разделе [Default](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Объявление свойства по умолчанию  
  
1. Объявите свойство обычным способом. Не указывайте ключевое слово `Shared` или `Private`.  
  
2. Включите ключевое слово `Default` в объявление свойства.  
  
3. Укажите по меньшей мере один параметр для свойства. Нельзя определить свойство по умолчанию, которое не принимает по крайней мере один аргумент.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>Вызов свойства по умолчанию  
  
1. Объявите переменную содержащего класса или типа структуры.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. Используйте только имя переменной в выражении, в которое вы обычно включаете имя свойства.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. Используйте имя переменной со списком аргументов в круглых скобках. Свойство по умолчанию должно принимать по крайней мере один аргумент.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. Чтобы получить значение свойства по умолчанию, используйте имя переменной со списком аргументов в выражении или после знака равенства (`=`) в операторе присваивания.  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. Чтобы задать значение свойства по умолчанию, используйте имя переменной со списком аргументов в левой части оператора присваивания.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. Вы всегда можете указать имя свойства по умолчанию вместе с именем переменной, как и при доступе к любому другому свойству.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется свойство по умолчанию для класса.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как вызвать свойство по умолчанию `myProperty` для класса `class1`. Три оператора присваивания хранят значения в `myProperty`, а <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов считывает значения.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 Наиболее распространенным применением свойства по умолчанию является свойство <xref:Microsoft.VisualBasic.Collection.Item%2A> для различных классов коллекций.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Свойства по умолчанию могут привести к небольшому сокращению количества символов в исходном коде, но они могут усложнить чтение кода. Если вызывающий код не знаком с классом или структурой, то при создании ссылки на имя класса или структуры он не может определить, обращается ли эта ссылка к самому классу или структуре, или к свойству по умолчанию. Это может привести к ошибкам компилятора или незначительным логическим ошибкам времени выполнения.  
  
 Можно немного уменьшить вероятность ошибок свойств по умолчанию, всегда используя [оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) , чтобы установить проверку типа компилятора на `On`.  
  
 Если вы планируете использовать в коде предопределенный класс или структуру, необходимо определить, имеет ли он свойство по умолчанию, и, если да, то, какое имя имеет значение.  
  
 Из-за этих недостатков рекомендуется не определять свойства по умолчанию. Для удобочитаемости кода следует также рассмотреть возможность явной ссылки на все свойства, даже свойства по умолчанию.  
  
## <a name="see-also"></a>См. также

- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Default](../../../../visual-basic/language-reference/modifiers/default.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создание свойства](./how-to-create-a-property.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)
- [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
- [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
