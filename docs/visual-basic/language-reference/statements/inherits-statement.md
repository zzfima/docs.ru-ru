---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 43a8aa4e9e04ee035cb52e9f829de13e5c022217
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604345"
---
# <a name="inherits-statement"></a>Inherits Statement
Вызывает текущий класс или интерфейс для наследования атрибутов, переменных, свойства, процедуры и события из другого класса или набора интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`basetypenames`|Обязательно. Имя класса, из которого происходит данный класс.<br /><br /> - или -<br /><br /> Имена интерфейсов, из которых производится данный интерфейс. Используйте запятые для разделения нескольких имен.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `Inherits` инструкция должна быть первой непустой незакомментированной строкой в определении класса или интерфейса. Он должен следовать непосредственно за `Class` или `Interface` инструкции.  
  
 Можно использовать `Inherits` только в классе или интерфейсе. Это означает, что контекст объявления для наследования не может быть исходный файл, пространство имен, структура, модуль, процедуры или блока.  
  
## <a name="rules"></a>Правила  
  
-   **Наследование классов.** Если класс использует `Inherits` инструкции, можно указать только один базовый класс.  
  
     Класс не может наследовать от вложенного в него класса.  
  
-   **Наследование интерфейса.** Если интерфейс использует `Inherits` инструкции, можно указать один или несколько базовых интерфейсов. Можно наследовать от двух интерфейсов, даже если каждый из них определяют член с тем же именем. При этом код реализации должен использовать уточнение имени, чтобы указать, какие члены, он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более строгим уровнем доступа. Например `Public` интерфейс не может наследовать от `Friend` интерфейса.  
  
     Интерфейс не может наследовать от интерфейса, вложенного в него.  
  
 Пример наследования класса в .NET Framework — <xref:System.ArgumentException> класс, унаследованный от класса <xref:System.SystemException> класса. Это обеспечивает с <xref:System.ArgumentException> стандартные свойства и процедуры, необходимые в исключениях системы, такие как <xref:System.Exception.Message%2A> свойство и <xref:System.Exception.ToString%2A> метод.  
  
 Пример наследования интерфейса в .NET Framework — <xref:System.Collections.ICollection> интерфейс, который наследует от <xref:System.Collections.IEnumerable> интерфейса. В результате <xref:System.Collections.ICollection> наследование определения требуется, выполняющие перебор коллекции перечислителя.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Inherits` инструкцию, чтобы показать, как класс с именем `thisClass` может наследовать все члены базового класса с именем `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано наследование от нескольких интерфейсов.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 Интерфейс, с именем `thisInterface` теперь включает все определения в <xref:System.IComparable>, <xref:System.IDisposable>, и <xref:System.IFormattable> интерфейсы наследуемые члены предоставляют соответственно для сравнения двух объектов, освобождая ресурсы выделяются и задание значения объекта как `String`. Класс, реализующий `thisInterface` необходимо реализовать каждый член каждого базового интерфейса.  
  
## <a name="see-also"></a>См. также  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
