---
title: "namespace (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "namespace_CSharpKeyword"
  - "namespace"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "namespace - ключевое слово [C#]"
  - "область [C#]"
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# namespace (Справочник по C#)
Ключевое слово `namespace` используется для объявления область, которая содержит набор связанных объектов.  Можно использовать пространство имен для организации элементов кода, а затем создать глобальную уникальность типы.  
  
 [!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/csharp/namespace_1.cs)]  
  
## Заметки  
 В пространстве имен можно объявить один или несколько из следующих типов:  
  
-   другое пространство имен;  
  
-   [class](../../../csharp/language-reference/keywords/class.md)  
  
-   [interface](../../../csharp/language-reference/keywords/interface.md)  
  
-   [struct](../../../csharp/language-reference/keywords/struct.md)  
  
-   [enum](../../../csharp/language-reference/keywords/enum.md)  
  
-   [delegate](../../../csharp/language-reference/keywords/delegate.md)  
  
 Независимо от того, было ли в исходном файле на языке C\# объявлено пространство имен явным образом, компилятор добавляет пространство имен по умолчанию.  Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле.  Любой идентификатор в глобальном пространстве имен доступен для использования в любом имеющем имя пространстве имен.  
  
 Пространства имен неявно имеют общий доступ, и это невозможно изменить.  Описание модификаторов доступа, которые можно назначить элементам, входящим в пространство имен, см. в разделе [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Пространство имен можно определить в двух или нескольких объявлениях.  В следующем примере два класса определяются в качестве части пространства имен `MyCompany`:  
  
 [!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/csharp/namespace_2.cs)]  
  
## Пример  
 В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.  
  
 [!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/csharp/namespace_3.cs)]  
  
## Дополнительные сведения  
 Дополнительные сведения об использовании пространств имен см. в следующих разделах:  
  
-   [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [использование](../../../csharp/language-reference/keywords/using.md)