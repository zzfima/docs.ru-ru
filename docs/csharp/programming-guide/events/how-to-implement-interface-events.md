---
title: Руководство по программированию на C#. Реализация событий интерфейса
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 8c0d221ef1272a43e2682ef2af3fa37d2d12d35e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167484"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Руководство по программированию на C#. Реализация событий интерфейса
[Интерфейс](../../language-reference/keywords/interface.md) может объявлять [события](../../language-reference/keywords/event.md). Следующий пример демонстрирует реализацию событий интерфейса в классе. По сути правила остаются такими же, как при реализации любого метода или свойства интерфейса.  
  
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
Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует характеристики от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем. Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий. Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`. Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.  
  
Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям. Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе. В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [События](./index.md)
- [Делегаты](../delegates/index.md)
- [Явная реализация интерфейса](../interfaces/explicit-interface-implementation.md)
- [Практическое руководство. Создание событий базового класса в производных классах](./how-to-raise-base-class-events-in-derived-classes.md)
