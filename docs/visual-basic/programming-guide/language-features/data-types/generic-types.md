---
title: Универсальные типы
ms.date: 07/20/2015
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
ms.openlocfilehash: 3dcd7756b10fab8f66f4d5c10acedd8f600eb2e7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350124"
---
# <a name="generic-types-in-visual-basic-visual-basic"></a>Универсальные типы в Visual Basic (Visual Basic)
*Универсальный тип* является одиночным элементом программирования, который используется для выполнения одинаковой функциональности для различных типов данных. При определении универсальных классов или процедур не нужно определять отдельную версию для каждого типа данных, для которых может потребоваться выполнение этой функциональности.  
  
 В качестве аналогии можно привести отвертку со съемными головками. Вы смотрите на шуруп, который нужно завинтить, и выбираете подходящую головку (шлицевую, крестовую или звездообразную). Меняя головки, вы выполняете с помощью отвертки одну и ту же функцию: завинчиваете или вывинчиваете шуруп.  
  
 ![Diagram of a screwdriver set with different heads.](./media/generic-types/generic-screwdriver-set.gif)  
  
 При определении универсального типа его можно параметризовать с помощью одного или нескольких типов данных. Это позволяет использовать код, чтобы адаптировать типы данных к его требованиям. В коде можно объявить несколько различных элементов программирования из универсального элемента, каждый из которых действует для разных наборов типов данных. Но все объявленные элементы подчиняются одинаковой логике, независимо от того, какие типы данных они используют.  
  
 Допустим, вам нужно создать и использовать класс очереди, который работает с определенным типом данных, например `String`. Можно объявить такой класс из <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, как показано в следующем примере.  
  
 [!code-vb[VbVbalrDataTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#1)]  
  
 Теперь можно использовать `stringQ` для работы исключительно со значениями `String` . Так как `stringQ` предназначен конкретно для `String` , а не является универсальным для значений `Object` , вам не потребуется позднее связывание или преобразование типа. Это экономит время выполнения и сокращает число ошибок во время выполнения.  
  
 Дополнительные сведения об использовании универсального типа см. в разделе [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md).  
  
## <a name="example-of-a-generic-class"></a>Пример универсального класса  
 В следующем примере показано определение каркаса универсального класса.  
  
 [!code-vb[VbVbalrDataTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#2)]  
  
 В предыдущем каркасе `t` — это *параметр типа*, то есть заполнитель для типа данных, указанного при объявлении класса. В другом месте в коде можно объявлять различные версии `classHolder` , указав различные типы данных для `t`. Два таких объявления показаны в следующем примере.  
  
 [!code-vb[VbVbalrDataTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#3)]  
  
 Предыдущие инструкции объявляют *сконструированные классы*, в которых указанный тип заменяет параметр типа. Эта замена распространяется по всему коду сконструированного класса. В следующем примере показано, как процедура `processNewItem` выглядит в `integerClass`.  
  
 [!code-vb[VbVbalrDataTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#4)]  
  
 For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md).  
  
## <a name="eligible-programming-elements"></a>Допустимые элементы программирования  
 Можно определять и использовать универсальные классы, структуры, интерфейсы, процедуры и делегаты. Note that the .NET Framework defines several generic classes, structures, and interfaces that represent commonly used generic elements. Пространство имен <xref:System.Collections.Generic?displayProperty=nameWithType> предоставляет словари, списки, очереди и стеки. Перед определением собственного универсального элемента посмотрите, не существует ли он уже в <xref:System.Collections.Generic?displayProperty=nameWithType>.  
  
 Процедуры не являются типами, но можно определять и использовать универсальные процедуры. См. раздел [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="advantages-of-generic-types"></a>Преимущества универсальных типов  
 Универсальный тип служит в качестве основы для объявления нескольких различных программных элементов, каждый из которых работает с определенным типом данных. Альтернативы для универсального типа:  
  
1. одиночный тип, работающий с типом данных `Object` .  
  
2. Набор *типозависимых* версий типа; каждая версия кодируется индивидуально и работает с одним конкретным типом данных (например `String`, `Integer`) или с определяемым пользователем типом, например `customer`.  
  
 Универсальный тип имеет следующие преимущества по сравнению с этими альтернативами.  
  
- **Безопасность.** Универсальные типы обеспечивают проверку типов во время компиляции. Типы на основе `Object` принимают любой тип данных, и необходимо написать код, чтобы проверить, является ли тип входных данных приемлемым. При использовании универсальных типов компилятор может перехватить несоответствие типов до выполнения.  
  
- **Производительность.** Универсальные типы не должны *упаковывать* и *распаковывать* данные, так как каждый из них является специальным для одного типа данных. Операции, основанные на `Object` , должны упаковывать типы входных данных для их преобразования в `Object` и распаковать данные, предназначенные для вывода. Упаковка и распаковка снижают производительность.  
  
     Типы на основе `Object` имеют позднее связывание, а значит, для доступа к их элементам требуется дополнительный код во время выполнения. Это также снижает производительность.  
  
- **Консолидация кода.** Код в универсальном типе должен быть определен только один раз. Набор типозависимых версий типа должен реплицировать тот же код в каждой версии. Единственное отличие состоит в конкретном типе данных для этой версии. При использовании универсальных типов типозависимые версии формируются из исходного универсального типа.  
  
- **Повторное использование кода.** Код, который не зависит от определенного типа данных, можно повторно использовать с различными типами данных, если он является универсальным. Часто его можно повторно использовать даже с типом данных, который изначально не предусматривался.  
  
- **Поддержка IDE.** При использовании сконструированного типа, объявленного из универсального типа, интегрированная среда разработки (IDE) может предоставить дополнительную поддержку при разработке кода. Например, IntelliSense может показать типозависимые параметры аргумента для конструктора или метода.  
  
- **Универсальные алгоритмы.** Абстрактные алгоритмы, которые не зависят от типов, хорошо подходят для универсальных типов. Например, универсальную процедуру, которая сортирует элементы с помощью интерфейса <xref:System.IComparable> , можно использовать с любым типом данных, который реализует <xref:System.IComparable>.  
  
## <a name="constraints"></a>Ограничения  
 Несмотря на то, что код в определении универсального типа должен быть максимально независимым от типов, может потребоваться определенная возможность любого типа данных, указанного для универсального типа. Например, если необходимо сравнить два элемента с целью сортировки или упорядочивания, их тип данных должен реализовывать интерфейс <xref:System.IComparable> . Соблюдение этого требования можно обеспечить путем добавления *ограничения* к параметру типа.  
  
### <a name="example-of-a-constraint"></a>Пример ограничения  
 В следующем примере показано каркасное определение класса с ограничением, которое требует аргумент типа для реализации <xref:System.IComparable>.  
  
 [!code-vb[VbVbalrDataTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#5)]  
  
 Если последующий код попытается создать класс из `itemManager` , используя тип, который не реализует <xref:System.IComparable>, компилятор сообщит об ошибке.  
  
### <a name="types-of-constraints"></a>Типы ограничений  
 Ограничение может содержать приведенные ниже требования в любой комбинации.  
  
- Аргумент типа должен реализовывать один или несколько интерфейсов.  
  
- Аргумент типа должен наследовать только из одного класса или быть типом только одного класса.  
  
- Аргумент типа должен предоставлять конструктор без параметров, доступный коду, который создает объекты из него.  
  
- Аргумент типа должен быть *типом ссылки*или *типом значения*.  
  
 Если нужно задать более одного требования, используйте разделенный запятыми *список ограничений* , заключенный в фигурные скобки (`{ }`). To require an accessible constructor, you include the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the list. Чтобы требовать ссылочный тип, включите ключевое слово `Class` . Чтобы требовать тип значения, включите ключевое слово `Structure` .  
  
 Дополнительные сведения об ограничениях см. в разделе [Type List](../../../../visual-basic/language-reference/statements/type-list.md).  
  
### <a name="example-of-multiple-constraints"></a>Пример множественных ограничений  
 В следующем примере показано каркасное определение универсального класса со списком ограничений в параметре типа. В коде, который создает экземпляр этого класса, аргумент типа должен реализовывать интерфейсы <xref:System.IComparable> и <xref:System.IDisposable> , быть ссылочным типом и предоставлять доступ к конструктору без параметров.  
  
 [!code-vb[VbVbalrDataTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#6)]  
  
## <a name="important-terms"></a>Важные термины  
 Универсальные типы вводят и используют следующие термины.  
  
- *Универсальный тип*. Определение класса, структуры, интерфейса, процедуры или делегата, для которого необходимо указать по крайней мере один тип данных при объявлении.  
  
- *Параметр типа*. В определении универсального типа это заполнитель для типа данных, указываемый при объявлении типа.  
  
- *Аргумент типа*. Определенный тип данных, который заменяет параметр типа при объявлении сконструированного типа из универсального типа.  
  
- *Ограничение*. Условие для параметра типа, ограничивающее аргумент типа, который можно указать для него. Ограничение может требовать, чтобы аргумент типа реализовывал определенный интерфейс, был определенным классом или наследовал от него, имел доступный конструктор без параметров или был ссылочным типом или типом значения. Можно объединять эти ограничения, но невозможно указывать более одного класса.  
  
- *Сконструированный тип*. Класс, структура, интерфейс, процедура или делегат, объявленный из универсального типа с помощью указания аргументов типа для параметров типа.  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Of](../../../../visual-basic/language-reference/statements/of-clause.md)
- [As](../../../../visual-basic/language-reference/statements/as-clause.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Ковариация и контрвариантность](../../concepts/covariance-contravariance/index.md)
- [Итераторы](../../../../visual-basic/programming-guide/concepts/iterators.md)
