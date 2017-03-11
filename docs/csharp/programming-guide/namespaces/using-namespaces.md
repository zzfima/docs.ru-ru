---
title: "Использование пространств имен (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.names"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "полные имена [C#]"
  - "пространства имен [C#], использование"
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Использование пространств имен (Руководство по программированию в C#)
В программах на языке C\# пространства имен активно используются двумя способами.  Во\-первых, классами платформы .NET Framework пространства имен используются для организации большого числа классов.  Во\-вторых, объявление собственного пространства имен поможет в управлении областью действия имен классов и методов в крупных программных проектах.  
  
## Доступ к пространствам имен  
 Большинство приложений на языке C\# начинаются с раздела директив `using`.  В этом разделе перечисляются пространства имен, которые будут часто использоваться приложением, и это спасает программиста от необходимости указывать полное имя каждый раз, когда используется содержащийся в них метод.  
  
 Например, включив строку:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 в начале программы, программист может использовать код:  
  
 [!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#31)]  
  
 вместо кода:  
  
 [!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#30)]  
  
## Псевдонимы пространств имен  
 [Директива using](../../../csharp/language-reference/keywords/using-directive.md) также может использоваться для создания псевдонима [пространства имен](../../../csharp/language-reference/keywords/namespace.md).  Например, в случае использования написанного прежде пространства имен, содержащего вложенные пространства имен, можно объявить псевдоним для обеспечения быстрого способа обращения к одному из них, как показано в следующем примере:  
  
 [!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#7)]  
  
## Использование пространств имен для управления областью действия  
 Ключевое слово `namespace` используется для объявления области действия.  Возможность создавать области действия в рамках проекта помогает организовывать код и позволяет создавать глобально уникальные типы.  В следующем примере в двух пространствах имен, одно из которых вложено в другое, определяется класс, названный `SampleClass`.  Для того, чтобы различать, какой метод вызывается, используется [Оператор .](../../../csharp/language-reference/operators/member-access-operator.md).  
  
 [!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#8)]  
  
## Полные имена  
 Пространства имен и типы имеют уникальные названия, описываемые полными именами, показывающими логическую иерархию.  Например, инструкция `A.B` подразумевает, что `A` — это имя пространства имен или типа, а `B` — это вложенный в него тип.  
  
 В следующем примере показаны вложенные классы и пространства имен.  Полное имя указано в качестве примечания после каждой сущности.  
  
 [!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#9)]  
  
 В предыдущем фрагменте кода:  
  
-   пространство имен `N1` является членом глобального пространства имен.  Его полным именем является `N1`;  
  
-   пространство имен `N2` является членом пространства имен `N1`.  Его полным именем является `N1.N2`;  
  
-   класс `C1` является членом пространства имен `N1`.  Его полным именем является `N1.C1`;  
  
-   имя класса `C2` используется в этом коде два раза.  Однако полные имена являются уникальными.  Первый экземпляр класса `C2` объявлен внутри класса `C1`; следовательно, его полным именем является `N1.C1.C2`.  Второй экземпляр класса `C2` объявлен внутри пространства имен `N2`; следовательно, его полным именем является `N1.N2.C2`.  
  
 Используя предыдущий фрагмента кода, можно добавить новый член: класс `C3`, в пространство имен `N1.N2`, как показано ниже:  
  
 [!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#10)]  
  
 В общем, используйте ключевое слово `::` для обращения к псевдониму пространства имен или ключевое слово `global::` для обращения к глобальному пространству имен и ключевое слово `.` для уточнения типов или членов.  
  
 Ошибкой является использование ключевого слова `::` с псевдонимом, ссылающимся на тип, а не на пространство имен.  Примеры.  
  
 [!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#11)]  
  
 [!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#12)]  
  
 Обратите внимание, что ключевое слово `global` не является предопределенным псевдонимом. Следовательно, имя `global.X` не имеет какого\-либо специального значения.  Оно приобретает специальное значение только при использовании с ключевым словом `::`.  
  
 В случае определения псевдонима global создается предупреждение компилятора CS0440, поскольку ключевое слово `global::` всегда ссылается на глобальное пространство имен, а не на псевдоним.  Например, следующая строка приведет к генерированию предупреждения:  
  
 [!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#13)]  
  
 Использование ключевого слова `::` с псевдонимами является правильной методикой, защищающей от неожиданного введения дополнительных типов.  Рассмотрим, например, следующий фрагмент кода:  
  
 [!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#14)]  
  
 [!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#15)]  
  
 Этот код работает, но если в последующем будет введен тип `Alias`, то конструкция `Alias.` станет связана с этим типом.  Использование конструкции `Alias::Exception` гарантирует, что имя `Alias` будет обрабатываться как псевдоним пространства имен и не будет ошибочно принято за тип.  
  
 Дополнительные сведения о псевдониме `global` см. в разделе [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Оператор .](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)