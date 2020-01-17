---
title: Руководство по программированию на C#. Реализация событий интерфейса
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: b84b96245310bce557bcd3865e41cf152e7ae9df
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712342"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="8d6d6-102">Руководство по программированию на C#. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="8d6d6-102">How to implement interface events (C# Programming Guide)</span></span>
<span data-ttu-id="8d6d6-103">[Интерфейс](../../language-reference/keywords/interface.md) может объявлять [события](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="8d6d6-103">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="8d6d6-104">Следующий пример демонстрирует реализацию событий интерфейса в классе.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="8d6d6-105">По сути правила остаются таким же, как при реализации любого метода или свойства интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="8d6d6-106">Реализация событий интерфейса в классе</span><span class="sxs-lookup"><span data-stu-id="8d6d6-106">To implement interface events in a class</span></span>  
  
<span data-ttu-id="8d6d6-107">Объявите событие в классе и вызовите его, когда потребуется.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="8d6d6-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8d6d6-108">Example</span></span>  
<span data-ttu-id="8d6d6-109">Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="8d6d6-110">Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="8d6d6-111">Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="8d6d6-112">Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="8d6d6-113">Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="8d6d6-114">Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="8d6d6-115">В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="8d6d6-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="8d6d6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8d6d6-116">See also</span></span>

- [<span data-ttu-id="8d6d6-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8d6d6-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8d6d6-118">События</span><span class="sxs-lookup"><span data-stu-id="8d6d6-118">Events</span></span>](./index.md)
- [<span data-ttu-id="8d6d6-119">Делегаты</span><span class="sxs-lookup"><span data-stu-id="8d6d6-119">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="8d6d6-120">Явная реализация интерфейса</span><span class="sxs-lookup"><span data-stu-id="8d6d6-120">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="8d6d6-121">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="8d6d6-121">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
