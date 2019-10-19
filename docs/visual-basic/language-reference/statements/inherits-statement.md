---
title: Оператор Inherits (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: e92e12908c89bb7a0bf385a2122b0c8f1eb8a6f7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581756"
---
# <a name="inherits-statement"></a>Inherits Statement
Заставляет текущий класс или интерфейс наследовать атрибуты, переменные, свойства, процедуры и события из другого класса или набора интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`basetypenames`|Обязательный. Имя класса, от которого наследует этот класс.<br /><br /> \- или -<br /><br /> Имена интерфейсов, из которых наследуется этот интерфейс. Используйте запятые для разделения нескольких имен.|  
  
## <a name="remarks"></a>Заметки  
 При использовании оператор `Inherits` должен быть первой непустой строкой, не являющейся комментарием, в определении класса или интерфейса. Он должен следовать сразу за `Class` или инструкцией `Interface`.  
  
 @No__t_0 можно использовать только в классе или интерфейсе. Это означает, что контекст объявления для наследования не может быть исходным файлом, пространством имен, структурой, модулем, процедурой или блоком.  
  
## <a name="rules"></a>Правила  
  
- **Наследование класса.** Если класс использует инструкцию `Inherits`, можно указать только один базовый класс.  
  
     Класс не может наследовать от класса, вложенного в него.  
  
- **Наследование интерфейса.** Если интерфейс использует инструкцию `Inherits`, можно указать один или несколько базовых интерфейсов. Можно наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем. В этом случае реализующий код должен использовать уточнение имени, чтобы указать, какой член он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более узким уровнем доступа. Например, интерфейс `Public` не может наследовать от интерфейса `Friend`.  
  
     Интерфейс не может наследовать от вложенного в него интерфейса.  
  
 Примером наследования класса в .NET Framework является класс <xref:System.ArgumentException>, который наследуется от класса <xref:System.SystemException>. Это позволяет <xref:System.ArgumentException> все предопределенные свойства и процедуры, необходимые системным исключениям, такие как свойство <xref:System.Exception.Message%2A> и метод <xref:System.Exception.ToString%2A>.  
  
 Примером наследования интерфейса в .NET Framework является интерфейс <xref:System.Collections.ICollection>, который наследуется от интерфейса <xref:System.Collections.IEnumerable>. В результате <xref:System.Collections.ICollection> наследует определение перечислителя, необходимого для прохода по коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере используется оператор `Inherits`, чтобы продемонстрировать, как класс с именем `thisClass` может наследовать все члены базового класса с именем `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано наследование нескольких интерфейсов.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 Интерфейс с именем `thisInterface` теперь включает все определения в интерфейсах <xref:System.IComparable>, <xref:System.IDisposable> и <xref:System.IFormattable>. унаследованные члены предоставляют соответствующие типы для сравнения двух объектов, высвобождения выделенных ресурсов и выражения значения объект в качестве `String`. Класс, реализующий `thisInterface`, должен реализовывать каждый член каждого базового интерфейса.  
  
## <a name="see-also"></a>См. также

- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
