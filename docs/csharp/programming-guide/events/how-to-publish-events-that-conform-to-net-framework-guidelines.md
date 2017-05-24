---
title: "Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework (руководство по программированию в C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 6d529e60643966fbabd5290543146977b4dc83c5
ms.contentlocale: ru-ru
ms.lasthandoff: 03/24/2017

---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a>Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework (Руководство по программированию в C#)
Следующая процедура демонстрирует добавление событий, которые соответствуют стандартному шаблону [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] для классов и структур. Все события в библиотеке классов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] основаны на делегате <xref:System.EventHandler>, который определен следующим образом:  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] представляет общую версию этого делегата, <xref:System.EventHandler%601>. В следующих примерах демонстрируется использование обеих версий.  
  
 Хотя события в определяемых классах могут быть основаны на любом допустимом типе делегата, даже на делегатах, возвращающих значение, обычно рекомендуется основывать события на шаблоне [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] с помощью <xref:System.EventHandler>, как показано в следующем примере.  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a>Публикация событий, основанных на шаблоне EventHandler  
  
1.  (Пропустите этот шаг и перейдите к шагу 3a, если не нужно отправлять пользовательские данные с определенным событием.) Объявите класс для пользовательских данных в области, видимой для классов Publisher и Subscriber. Затем добавьте необходимые члены для хранения пользовательских данных о событиях. В этом примере возвращается простая строка.  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }   
    }  
    ```  
  
2.  (Пропустите этот шаг, если используется универсальная версия <xref:System.EventHandler%601>.) Объявите делегат в своем классе публикации. Присвойте ему имя, которое заканчивается на *EventHandler*. Второй параметр указывает настраиваемый тип EventArgs.  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  Объявите событие в своем классе публикации, выполнив одно из следующих действий.  
  
    1.  Если у вас нет пользовательского класса EventArgs, тип события будет неуниверсальным делегатом EventHandler. Нет необходимости объявлять делегат, так как он уже объявлен в пространстве имен <xref:System>, которое включается при создании проекта C#. Добавьте следующий код в класс Publisher.  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  Если вы используете неуниверсальную версию <xref:System.EventHandler>, и имеется пользовательский класс, производный от <xref:System.EventArgs>, объявите событие внутри класса публикации и используйте делегат из шага 2 в качестве типа.  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3.  Если используется универсальная версия, пользовательский делегат не требуется. Вместо этого в классе публикации укажите тип события как `EventHandler<CustomEventArgs>`, подставив имя своего класса в угловые скобки.  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a>Пример  
 В следующем примере показана вышеописанная процедура с использованием пользовательского класса EventArgs и <xref:System.EventHandler%601> в качестве типа событий.  
  
 [!code-cs[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-conform-to-net-framework-guidelines_1.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Delegate>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)
