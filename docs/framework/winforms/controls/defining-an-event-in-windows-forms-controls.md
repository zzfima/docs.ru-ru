---
title: Определение события в элементах управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: a4738373b10fbcb1d2406406d30f10b795aeb914
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228840"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="2a92e-102">Определение событий в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a92e-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="2a92e-103">Подробную информацию об определении пользовательских событий [можно](../../../standard/events/index.md)узнать на примере событий .</span><span class="sxs-lookup"><span data-stu-id="2a92e-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="2a92e-104">При определении события, не имеющего связанных данных, необходимо использовать базовый тип данных о событиях, <xref:System.EventArgs> и <xref:System.EventHandler> в качестве делегата события.</span><span class="sxs-lookup"><span data-stu-id="2a92e-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="2a92e-105">Остается только определить участника события и защищенный `On`метод *EventName,* который поднимает событие.</span><span class="sxs-lookup"><span data-stu-id="2a92e-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="2a92e-106">В следующем фрагменте кода показано, как пользовательский элемент управления `FlashTrackBar` определяет пользовательское событие, `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="2a92e-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="2a92e-107">Полный код для `FlashTrackBar` образца [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md)см.</span><span class="sxs-lookup"><span data-stu-id="2a92e-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate
   ' as the event delegate.
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged
   ' event when the value has actually
   ' changed. Derived controls can override this method.
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually
   // changed. Derived controls can override this method.
   protected virtual void OnValueChanged(EventArgs e)
   {  
       onValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a92e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2a92e-108">See also</span></span>

- [<span data-ttu-id="2a92e-109">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a92e-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="2a92e-110">События</span><span class="sxs-lookup"><span data-stu-id="2a92e-110">Events</span></span>](../../../standard/events/index.md)
