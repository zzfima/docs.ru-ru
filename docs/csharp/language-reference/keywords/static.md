---
title: "static (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "static"
  - "static_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "static - ключевое слово [C#]"
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# static (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту.  Модификатор `static` можно использовать с классами, полями, методами, свойствами, операторами, событиями и конструкторами, но нельзя — с индексаторами, деструкторами или типами, отличными от классов.  Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Пример  
 Следующий класс объявляется как `static` и содержит только `static` методы.  
  
 [!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 Объявление константы или типа неявно является статическим членом.  
  
 На статический член нельзя ссылаться через экземпляр.  а можно только через имя типа.  Например, рассмотрим следующий класс.  
  
 [!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 Чтобы создать ссылку на статический член `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` \(если только член не доступен из той же области действия\):  
  
```c#  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 Поскольку экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому статическому полю соответствует только одна копия.  
  
 [Так](../../../csharp/language-reference/keywords/this.md) нельзя ссылаться на статические методы или методы доступа к свойствам.  
  
 Если к классу применяется ключевое слово `static`, все члены этого класса должны быть статическими.  
  
 Классы и статические классы могут иметь статические конструкторы.  Статические конструкторы вызываются на определенном этапе между запуском программы и созданием экземпляра класса.  
  
> [!NOTE]
>  Ключевое слово `static` имеет более ограниченное применение по сравнению с C\+\+.  Сведения о сравнении с ключевым словом С\+\+ см. в разделе [Static](/visual-cpp/misc/static-cpp).  
  
 В качестве демонстрации статических членов рассмотрим класс, представляющий сотрудника компании.  Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа.  И метод, и поле не принадлежат никакому экземпляру сотрудника.  Они принадлежат классу компании.  В связи с этим они должны объявляться как статические члены класса.  
  
## Пример  
 В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и нового числа сотрудников.  Для простоты эта программа считывает текущее число сотрудников с клавиатуры.  В реальном приложении эта информация должна считываться из файла.  
  
 [!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## Пример  
 Этот пример показывает, что несмотря на то что вы можете инициализировать статическое поле посредством другого, еще не объявленного статического поля, результаты не будут определены до тех пор, пока статическому полю не будет явно присвоено значение.  
  
 [!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)