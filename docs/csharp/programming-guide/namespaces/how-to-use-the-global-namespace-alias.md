---
title: "Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "псевдонимы [C#]"
  - "глобальное пространство имен [C#]"
  - "пространства имен [C#], квалификатор глобального пространства имен"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#)
Возможность доступа к члену в глобальном [пространстве имен](../../../csharp/language-reference/keywords/namespace.md) полезна, когда этот член может быть скрыт другой сущностью с таким же именем.  
  
 Например, в следующем коде `Console` разрешается в тип `TestApp.Console` вместо типа `Console` в пространстве имен <xref:System>.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 При использовании `System.Console` все равно возникает ошибка, так как пространство имен `System` скрыто классом `TestApp.System`:  
  
 [!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 Однако данную ошибку можно устранить следующим образом, используя `global::System.Console`:  
  
 [!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Когда левый идентификатор имеет значение `global`, поиск правого идентификатора начинается в глобальном пространстве имен.  Например, следующее объявление ссылается на `TestApp` как на член глобального пространства.  
  
 [!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Очевидно, что необходимость в создании пространства имен `System` отсутствует, а вероятность повстречать код, где это сделано, очень мала.  Однако в более крупных проектах существует большая вероятность встретить ту или иную форму дублирования пространства имен.  В такой ситуации квалификатор глобального пространства имен является гарантирует возможность задания корневого пространства имен.  
  
## Пример  
 В данном примере пространство имен `System` используется для включения класса `TestClass`, поэтому для создания ссылки на класс `System.Console`, скрытый пространством имен `System`, необходимо использовать `global::System.Console`.  Кроме того, псевдоним `colAlias` используется для создания ссылки на пространство имен `System.Collections`; таким образом при создании экземпляра <xref:System.Collections.Hashtable?displayProperty=fullName> вместо пространства имен использовался этот псевдоним.  
  
 [!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
  **А 1**  
**В 2**  
**С 3**   
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Оператор .](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)