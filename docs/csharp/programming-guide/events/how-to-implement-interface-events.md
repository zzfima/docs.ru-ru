---
title: Практическое руководство. Реализация событий интерфейса (руководство по программированию на C#)
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
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Практическое руководство. Реализация событий интерфейса (руководство по программированию на C#)
[Интерфейс](../../../csharp/language-reference/keywords/interface.md) может объявлять [события](../../../csharp/language-reference/keywords/event.md). Следующий пример демонстрирует реализацию событий интерфейса в классе. По сути правила остаются таким же, как при реализации любого метода или свойства интерфейса.  
  
## <a name="to-implement-interface-events-in-a-class"></a>Реализация событий интерфейса в классе  
  
Объявите событие в классе и вызовите его, когда потребуется.  
  
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
  
## <a name="example"></a>Пример  
Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем. Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий. Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`. Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.  
  
Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям. Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе. В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [События](../../../csharp/programming-guide/events/index.md)
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)
- [Явная реализация интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)
- [Практическое руководство. Создание событий базового класса в производных классах](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
