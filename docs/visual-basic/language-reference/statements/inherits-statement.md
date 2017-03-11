---
title: "Инструкция Inherits | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Inherits"
  - "Inherits"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "оператор Inherits"
  - "оператор Inherits, синтаксис"
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Инструкция Inherits
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Вызывает текущий класс или интерфейс для наследования атрибутов, переменных, свойств, процедур и событий из другого класса или набора интерфейсов.  
  
## Синтаксис  
  
```  
Inherits basetypenames  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`basetypenames`|Обязательный.  Имя класса, от которого наследует данный класс.<br /><br /> \-или\-<br /><br /> Имена интерфейсов, из которых выводится данный интерфейс.  Используйте запятые для разделения нескольких имен.|  
  
## Заметки  
 При применении оператора `Inherits` он должен быть в объявлении класса или интерфейса первой непустой строкой, не учитывая строки примечаний.  Он должен следовать непосредственно за инструкциями `Class` или `Interface`.  
  
 Можно использовать `Inherits` только в классе или интерфейсе.  Это означает, что контекст объявления для наследования не может быть исходным файлом, пространством имен, структурой, модулем, процедурой или блоком.  
  
## Правила  
  
-   **Наследование классов.** Если класс использует инструкцию `Inherits`, можно указать только один базовый класс.  
  
     Класс не может наследовать от вложенного в него класса.  
  
-   **Наследование интерфейса** Если интерфейс использует оператор `Inherits`, то можно указать один или более базовых интерфейсов.  Можно наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем.  В таком случае код реализации должен использовать уточнение имени, чтобы указать, какие члены реализуются.  
  
     Интерфейс не может наследовать от другого интерфейса с более строгим уровнем доступа.  Например, интерфейс `Public` не может наследовать от интерфейса `Friend`.  
  
     Интерфейс не может наследовать от интерфейса, вложенного в него.  
  
 Примером наследования классов в .NET Framework является класс <xref:System.ArgumentException>, наследующий от класса <xref:System.SystemException>.  Это обеспечивает для <xref:System.ArgumentException> все стандартные свойства и процедуры, необходимые системе исключений, такие как свойство <xref:System.Exception.Message%2A> и метод <xref:System.Exception.ToString%2A>.  
  
 Примером наследования интерфейсов в .NET Framework является интерфейс <xref:System.Collections.ICollection>, наследующий от интерфейса <xref:System.Collections.IEnumerable>.  Благодаря этому <xref:System.Collections.ICollection> наследует определения перечислителя, необходимого для пересечения коллекции.  
  
## Пример  
 В следующем примере используется оператор `Inherits` для отображения наследования классом с именем `thisClass` всех членов базового класса с именем `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/inherits-statement_1.vb)]  
  
## Пример  
 В следующем примере показано наследование от нескольких интерфейсов.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/inherits-statement_2.vb)]  
  
 Интерфейс с именем `thisInterface` теперь включает все определения в интерфейсах <xref:System.IComparable>, <xref:System.IDisposable> и <xref:System.IFormattable>. Наследуемые члены обеспечиваются соответственно для сравнения определенного типа двух объектов, освобождая выделенные ресурсы и задавая значение объекта `String`.  Класс, реализующий `thisInterface`, должен реализовать каждый член каждого базового интерфейса.  
  
## См. также  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)