---
title: "Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "события [C#], правила реализации"
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework (Руководство по программированию в C#)
В следующей процедуре показано добавление событий, соответствующих стандартному шаблону [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] для пользовательских классов и структур.  Все события в библиотеке классов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] основаны на делегате <xref:System.EventHandler>, заданном следующим образом:  
  
```  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] представляет общую версию данного делегата <xref:System.EventHandler%601>.  В следующих примерах показано, как использовать обе версии.  
  
 Хотя события в задаваемых классах могут быть основаны на действительном типе делегата, даже на делегатах, возвращающих значение, обычно рекомендуется основывать события на шаблоне [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], используя <xref:System.EventHandler>, как показано в следующем примере.  
  
### Порядок публикации событий, основанных на шаблоне EventHandler  
  
1.  \(Пропустите этот шаг и перейдите к шагу 3a, если не требуется передавать с событием пользовательские данные.\) Объявите класс для пользовательских данных в области, видимой для классов издателя и подписчика.  Затем добавьте необходимые члены для хранения данных пользовательских событий.  В данном примере возвращается простая строка.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
2.  \(Пропустите данный шаг, если используется общая версия <xref:System.EventHandler%601> .\) Объявите делегат в своем классе публикации.  Назначьте ему имя, заканчивающееся на *EventHandler*.  Второй параметр задает ваш тип EventArgs.  
  
    ```  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  Объявите событие в своем классе публикации с помощью одного из следующих действий.  
  
    1.  Если пользовательский класс EventArgs отсутствует, ваш тип Event представляет собой не являющийся общим делегат EventHandler.  Этот делегат не нужно объявлять, так как он уже объявлен в пространстве имен <xref:System>, добавленном при создании проекта C\#.  Добавьте следующий код в класс издателя.  
  
        ```  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  При использовании не универсальной версии типа <xref:System.EventHandler> и наличии пользовательского класса, производного от типа <xref:System.EventArgs>, объявите событие внутри класса публикации и используйте делегат из пункта 2 в качестве типа.  
  
        ```  
        public event CustomEventHandler RaiseCustomEvent;  
  
        ```  
  
    3.  Если используется универсальная версия, то пользовательский делегат не требуется.  Вместо этого в классе публикации необходимо задать тип события как `EventHandler<CustomEventArgs>`, заключив имя пользовательского класса в угловые скобки.  
  
        ```  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## Пример  
 В следующем примере демонстрируются предыдущие шаги с применением пользовательского класса EventArgs и типа <xref:System.EventHandler%601> в качестве типа события.  
  
 [!code-cs[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-conform-to-net-framework-guidelines_1.cs)]  
  
## См. также  
 <xref:System.Delegate>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)