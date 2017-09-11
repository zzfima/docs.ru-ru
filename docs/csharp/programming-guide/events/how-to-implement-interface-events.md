---
title: "Практическое руководство. Реализация событий интерфейса (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8f8460674aa59170cf75eb2fa93e9d232df07e5e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="642f5-102">Практическое руководство. Реализация событий интерфейса (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="642f5-102">How to: Implement Interface Events (C# Programming Guide)</span></span>
<span data-ttu-id="642f5-103">[Интерфейс](../../../csharp/language-reference/keywords/interface.md) может объявлять [события](../../../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="642f5-103">An [interface](../../../csharp/language-reference/keywords/interface.md) can declare an [event](../../../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="642f5-104">Следующий пример демонстрирует реализацию событий интерфейса в классе.</span><span class="sxs-lookup"><span data-stu-id="642f5-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="642f5-105">По сути правила остаются таким же, как при реализации любого метода или свойства интерфейса.</span><span class="sxs-lookup"><span data-stu-id="642f5-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
### <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="642f5-106">Реализация событий интерфейса в классе</span><span class="sxs-lookup"><span data-stu-id="642f5-106">To implement interface events in a class</span></span>  
  
-   <span data-ttu-id="642f5-107">Объявите событие в классе и вызовите его, когда потребуется.</span><span class="sxs-lookup"><span data-stu-id="642f5-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="642f5-108">Пример</span><span class="sxs-lookup"><span data-stu-id="642f5-108">Example</span></span>  
 <span data-ttu-id="642f5-109">Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="642f5-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="642f5-110">Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий.</span><span class="sxs-lookup"><span data-stu-id="642f5-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="642f5-111">Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`.</span><span class="sxs-lookup"><span data-stu-id="642f5-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="642f5-112">Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.</span><span class="sxs-lookup"><span data-stu-id="642f5-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
 <span data-ttu-id="642f5-113">Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям.</span><span class="sxs-lookup"><span data-stu-id="642f5-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="642f5-114">Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе.</span><span class="sxs-lookup"><span data-stu-id="642f5-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="642f5-115">В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="642f5-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 <span data-ttu-id="642f5-116">[!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="642f5-116">[!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642f5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="642f5-117">See Also</span></span>  
 <span data-ttu-id="642f5-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="642f5-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="642f5-119">[События](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="642f5-119">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="642f5-120">[Делегаты](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="642f5-120">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="642f5-121">[Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="642f5-121">[Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) </span></span>  
 [<span data-ttu-id="642f5-122">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="642f5-122">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)

