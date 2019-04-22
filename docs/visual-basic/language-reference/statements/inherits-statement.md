---
title: Наследует Statement (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 5ab90e44e2809c1e71d7f100970b7be73af4a732
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817101"
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
|`basetypenames`|Обязательный. Имя класса, из которого происходит данный класс.<br /><br /> -или-<br /><br /> Имена интерфейсов, от которых наследует этот интерфейс. Используйте запятые для разделения нескольких имен.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `Inherits` инструкция должна быть первой непустой строкой, не являющихся комментариями строки в определении класса или интерфейса. Он должен следовать непосредственно за `Class` или `Interface` инструкции.  
  
 Можно использовать `Inherits` только в классе или интерфейсе. Это означает, что контекст объявления для наследования не может быть исходный файл, пространство имен, структура, модуль, процедуры или блока.  
  
## <a name="rules"></a>Правила  
  
-   **Наследование классов.** Если класс использует `Inherits` инструкции, можно указать только один базовый класс.  
  
     Класс не может наследовать от вложенного в него класса.  
  
-   **Наследование интерфейса.** Если интерфейс использует `Inherits` инструкции, можно указать один или несколько базовых интерфейсов. Может наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем. Если сделать это, код реализации необходимо использовать уточнение имен, чтобы указать, какие члены, он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более строгий уровень доступа. Например `Public` интерфейс не может наследовать от `Friend` интерфейс.  
  
     Интерфейс не может наследовать от вложенного в него интерфейс.  
  
 Пример наследования классов в .NET Framework — <xref:System.ArgumentException> класс, унаследованный от <xref:System.SystemException> класса. Это обеспечивает <xref:System.ArgumentException> все стандартные свойства и процедуры, необходимые системные исключения, такие как <xref:System.Exception.Message%2A> свойство и <xref:System.Exception.ToString%2A> метод.  
  
 Пример наследования интерфейса в .NET Framework — <xref:System.Collections.ICollection> интерфейс, который наследует от <xref:System.Collections.IEnumerable> интерфейс. В результате <xref:System.Collections.ICollection> наследование определении перечислителя, который требуется для просмотра коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Inherits` инструкцию, чтобы показать, как класс с именем `thisClass` может наследовать все члены базового класса с именем `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано наследование от нескольких интерфейсов.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 Интерфейс, с именем `thisInterface` теперь включает все определения в <xref:System.IComparable>, <xref:System.IDisposable>, и <xref:System.IFormattable> интерфейсы, наследуемые члены предоставляют соответственно для сравнения двух объектов освобождения выделенных ресурсов и выражения значение объекта как `String`. Класс, реализующий `thisInterface` должен реализовать каждый член каждого базового интерфейса.  
  
## <a name="see-also"></a>См. также

- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
