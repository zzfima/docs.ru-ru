---
title: "Практическое руководство. Реализация событий интерфейса (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "события [C#], в интерфейсах"
  - "интерфейсы [C#], реализация событий в классах"
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Реализация событий интерфейса (Руководство по программированию в C#)
[Интерфейс](../../../csharp/language-reference/keywords/interface.md) может объявить [событие](../../../csharp/language-reference/keywords/event.md).  В следующем примере показана реализация событий интерфейса в классе.  В принципе, применяются те же правила, что и при реализации любого метода интерфейса или свойства.  
  
### Реализация событий интерфейса в классе  
  
-   Объявите событие в классе и вызовите его в соответствующих областях.  
  
    ```  
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## Пример  
 В следующем примере показано, как действовать в не очень распространенном случае, когда класс наследует от двух или более интерфейсов и каждый интерфейс имеет событие с тем же именем.  В такой ситуации, по меньшей мере, для одного из событий следует предоставить явную реализацию интерфейса.  При написании явной реализации интерфейса для события необходимо также написать методы доступа к событию `add` и `remove`.  Как правило, они обеспечиваются компилятором, в этом случае компилятор не сможет предоставить их.  
  
 При помощи собственных методов доступа можно определить, будут ли два события представлены одним событием в классе или разными событиями.  Например, если события должны инициироваться в разное время в зависимости от требований интерфейса, то каждое событие можно связать с отдельной реализацией в классе.  В следующем примере подписчики определяют, какое событие `OnDraw` они получат путем приведения ссылки на форму к `IShape` или `IDrawingObject`.  
  
 [!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/csharp/how-to-implement-interfa_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)   
 [Практическое руководство. Создание событий базового класса в производных классах](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)