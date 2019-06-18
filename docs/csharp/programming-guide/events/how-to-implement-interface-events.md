---
title: Как реализовать события интерфейса (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: dfd0602ef92f9b0f84a8e1434ef834a328d60f03
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200277"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="3927e-102">Как реализовать события интерфейса (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3927e-102">How to: Implement Interface Events (C# Programming Guide)</span></span>
<span data-ttu-id="3927e-103">[Интерфейс](../../../csharp/language-reference/keywords/interface.md) может объявлять [события](../../../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="3927e-103">An [interface](../../../csharp/language-reference/keywords/interface.md) can declare an [event](../../../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="3927e-104">Следующий пример демонстрирует реализацию событий интерфейса в классе.</span><span class="sxs-lookup"><span data-stu-id="3927e-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="3927e-105">По сути правила остаются таким же, как при реализации любого метода или свойства интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3927e-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="3927e-106">Реализация событий интерфейса в классе</span><span class="sxs-lookup"><span data-stu-id="3927e-106">To implement interface events in a class</span></span>  
  
<span data-ttu-id="3927e-107">Объявите событие в классе и вызовите его, когда потребуется.</span><span class="sxs-lookup"><span data-stu-id="3927e-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
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
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="3927e-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3927e-108">Example</span></span>  
<span data-ttu-id="3927e-109">Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="3927e-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="3927e-110">Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий.</span><span class="sxs-lookup"><span data-stu-id="3927e-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="3927e-111">Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`.</span><span class="sxs-lookup"><span data-stu-id="3927e-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="3927e-112">Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.</span><span class="sxs-lookup"><span data-stu-id="3927e-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="3927e-113">Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям.</span><span class="sxs-lookup"><span data-stu-id="3927e-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="3927e-114">Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе.</span><span class="sxs-lookup"><span data-stu-id="3927e-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="3927e-115">В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="3927e-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="3927e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3927e-116">See also</span></span>

- [<span data-ttu-id="3927e-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3927e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3927e-118">События</span><span class="sxs-lookup"><span data-stu-id="3927e-118">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="3927e-119">Делегаты</span><span class="sxs-lookup"><span data-stu-id="3927e-119">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="3927e-120">Явная реализация интерфейса</span><span class="sxs-lookup"><span data-stu-id="3927e-120">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="3927e-121">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="3927e-121">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
