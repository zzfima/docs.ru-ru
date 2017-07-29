---
title: "Объекты (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- objects [C#], about objects
- variables [C#]
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a2a23d02e4ea95e908f97bc7264ee64d6899aee8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="objects-c-programming-guide"></a>Объекты (Руководство по программированию на C#)
Определение класса или структуры подобно чертежу, на котором указаны действия, выполняемые типом. В сущности, объект является блоком памяти, выделенной и настроенной в соответствии с чертежом. Программа может создать множество объектов одного класса. Объекты также называют экземплярами. Они могут храниться либо в именованной переменной, либо в массиве или коллекции. Клиентский код — это код, использующий эти переменные для вызова методов и доступа к открытым свойствам объекта. В объектно-ориентированном языке, таком как C#, стандартная программа состоит из нескольких динамически взаимодействующих объектов.  
  
> [!NOTE]
>  Поведение статических типов отличается от описанного здесь поведения. Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## <a name="struct-instances-vs-class-instances"></a>Экземпляры структуры и Экземпляры классов  
 Так как классы являются ссылочными типами, в переменной объекта класса хранится ссылка на адрес объекта в управляемой куче. Если первому объекту назначен второй объект того же типа, обе переменные ссылаются на объект, расположенный по данному адресу. Эта особенность обсуждается более подробно далее в этом разделе.  
  
 Экземпляры классов создаются с помощью [оператора new](../../../csharp/language-reference/keywords/new-operator.md). В приведенном ниже примере `Person` является типом, а `person1` и `person 2` — экземплярами или объектами этого типа.  
  
 [!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]  
  
 Так как структуры являются типами значений, в переменной объекта структуры хранится копия всего объекта. Экземпляры структур также можно создавать с помощью оператора `new`, однако он не является обязательным, как показано в следующем примере:  
  
 [!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]  
  
 Память для `p1` и `p2` выделена в стеке потока. Эта память освобождается вместе с типом или методом, в котором она объявляется. Эта одна из причин того, почему структуры копируются при присваивании. Напротив, при выходе всех ссылок на объект из области действия среда CLR автоматически освобождает память (выполняет сборку мусора), выделенную для экземпляра класса. Возможность детерминированного уничтожения объекта класса, имеющаяся в C++, в данном случае отсутствует. Дополнительные сведения о сборке мусора в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] см. в разделе [Сборка мусора](../../../standard/garbage-collection/index.md).  
  
> [!NOTE]
>  В среде CLR процесс выделения и освобождения памяти в управляемой куче значительно оптимизирован. В большинстве случаев нет существенной разницы в затратах производительности на выделение экземпляра класса в куче и выделение экземпляра структуры в стеке.  
  
## <a name="object-identity-vs-value-equality"></a>Идентификация объектов и равенство значений  
 Сравнивая два объекта на предмет равенства, сначала необходимо определить, нужно ли узнать, представляют ли две переменные один объект в памяти или значения одного или нескольких их полей являются равными. Если вы планируете сравнить значения, следует решить, являются ли объекты экземплярами типов значений (структурами) или ссылочными типами (классами, делегатами, массивами).  
  
-   Чтобы определить, ссылаются ли два экземпляра класса на одно расположение в памяти (то есть имеют одинаковый *идентификатор*), воспользуйтесь статическим методом <xref:System.Object.Equals%2A>. (<xref:System.Object?displayProperty=fullName> является неявным базовым классом для всех типов значений и ссылочных типов, включая структуры и классы, определенные пользователем.)  
  
-   Чтобы определить, имеют ли поля экземпляра в двух экземплярах структуры одинаковые значения, воспользуйтесь методом <xref:System.ValueType.Equals%2A?displayProperty=fullName>. Так как все структуры неявно наследуются от <xref:System.ValueType?displayProperty=fullName>, метод можно вызвать непосредственно в объекте, как показано в следующем примере:  
  
 [!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]  
  
 В реализации <xref:System.ValueType?displayProperty=fullName> `Equals` используется отражение, так как необходимо определить поля, имеющиеся в любой структуре. При создании собственных структур переопределите метод `Equals` для предоставления эффективного алгоритма равенства, соответствующего вашему типу.  
  
-   Чтобы определить, равны ли значения полей в двух экземплярах класса, можно воспользоваться методом <xref:System.Object.Equals%2A> или [оператором ==](../../../csharp/language-reference/operators/equality-comparison-operator.md). Однако их следует использовать, только если они переопределены или перегружены классом с целью предоставления пользовательского определение равенства для объектов этого типа. Класс может также реализовывать интерфейс <xref:System.IEquatable%601> или интерфейс <xref:System.Collections.Generic.IEqualityComparer%601>. Оба интерфейса предоставляют методы, которые можно использовать для проверки равенства значений. При создании собственных классов, переопределяющих `Equals`, следует выполнять инструкции из разделов [Практическое руководство. Определение равенства значений для типа ](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md) и <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [События](../../../csharp/programming-guide/events/index.md)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [class](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [Оператор new](../../../csharp/language-reference/keywords/new-operator.md)   
 [Система общих типов CTS](../../../standard/base-types/common-type-system.md)

