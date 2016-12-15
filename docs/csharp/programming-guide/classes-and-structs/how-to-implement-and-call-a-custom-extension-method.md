---
title: "Практическое руководство. Реализация и вызов пользовательского метода расширения (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "методы расширения [C#], реализация и вызов"
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Реализация и вызов пользовательского метода расширения (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом разделе показано, как реализовать собственные методы расширения для любого типа в [Библиотека классов .NET Framework](http://go.microsoft.com/fwlink/?LinkID=217856)или любой другой тип .NET, который требуется расширить.  Клиентский код может использовать собственные методы расширения путем добавления ссылки на библиотеку DLL с этими методами, и добавления директивы [using](../../../csharp/language-reference/keywords/using-directive.md), определяющей пространство имен, в котором определены методы расширения.  
  
### Определение и вызов метода расширения  
  
1.  Определите статический [класс](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md), который будет содержать метод расширения.  
  
     Класс должен быть видимым для клиентского кода.  Дополнительные сведения о правилах доступности см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2.  Реализуйте метод расширения в качестве статического метода, обладающего, по меньшей мере, такой же видимостью, что и содержащий класс.  
  
3.  Первый параметр метода определяет тип, с которым метод выполняет операции; ему должен предшествовать модификатор [this](../../../csharp/language-reference/keywords/this.md).  
  
4.  В вызывающем коде добавьте директиву `using`, чтобы указать [пространство имен](../../../csharp/language-reference/keywords/namespace.md) с классом метода расширения.  
  
5.  Вызовите методы, как если бы они были методами экземпляра в типе.  
  
     Обратите внимание, что первый параметр не указывается вызывающим кодом, так как представляет тип, к которому применяется оператор, и компилятору уже известен тип объекта.  Аргументы нужно указать только для параметров со 2 по `n`.  
  
## Пример  
 Следующий пример реализует метод расширения с именем `WordCount` в классе `CustomExtensions.StringExtension`.  Метод выполняет операции с классом <xref:System.String>, указанным в первом параметре метода.  Пространство имен `CustomExtensions` импортируется в пространство имен приложения, и метод вызывается внутри метода `Main`.  
  
 [!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## Компиляция кода  
 Для выполнения этого кода скопируйте его в проект консольного приложения на языке Visual C\#, которое было создано в среде разработки [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)].  По умолчанию этот проект предназначен для версии 3.5 платформы [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и имеет ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq.  Если одно или более требований в проекте отсутствуют, их можно добавить вручную.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Безопасность платформы .NET Framework  
 Методы расширения не представляют определенных уязвимостей безопасности.  Они ни в коем случае не могут использоваться для олицетворения существующих методов в типе, поскольку все конфликты имен разрешаются в пользу метода экземпляра или статического метода, определяемого самим типом.  Методы расширения не могут обращаться к каким\-либо закрытым данным в расширенном классе.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [защищенные](../../../csharp/language-reference/keywords/protected.md)   
 [внутренние](../../../csharp/language-reference/keywords/internal.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [this](../../../csharp/language-reference/keywords/this.md)   
 [пространство имен](../../../csharp/language-reference/keywords/namespace.md)