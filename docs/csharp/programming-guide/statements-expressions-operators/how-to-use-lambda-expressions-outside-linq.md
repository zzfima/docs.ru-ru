---
title: "Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "лямбда-выражения [C#], вне LINQ"
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Практическое руководство. Использование лямбда-выражений вне LINQ (Руководство по программированию на C#)
Лямбда\-выражения не ограничиваются запросами [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  Их можно использовать везде, где ожидается значение\-делегат, то есть везде, где можно использовать анонимные методы.  В следующем примере показано, как использовать лямбда\-выражение в обработчике событий Windows Forms.  Обратите внимание, что входные типы \(<xref:System.Object> и <xref:System.Windows.Forms.MouseEventArgs>\) выводятся компилятором, их не нужно явным образом указывать во входных параметрах лямбда\-выражения.  
  
## Пример  
  
```  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## См. также  
 [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)