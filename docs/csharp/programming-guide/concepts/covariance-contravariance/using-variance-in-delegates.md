---
title: Использование вариативности в делегатах (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 83e86e760edb17f6d9ae61864c154062d41416e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169770"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="5dc62-102">Использование вариативности в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="5dc62-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="5dc62-103">При назначении метода делегату *ковариация* и *контравариантость* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода.</span><span class="sxs-lookup"><span data-stu-id="5dc62-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="5dc62-104">Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в делегате.</span><span class="sxs-lookup"><span data-stu-id="5dc62-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="5dc62-105">Контравариантность позволяет использовать метод с типами параметров, степень наследования которых меньше, чем у типа делегата.</span><span class="sxs-lookup"><span data-stu-id="5dc62-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="5dc62-106">Пример 1. Ковариация</span><span class="sxs-lookup"><span data-stu-id="5dc62-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="5dc62-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5dc62-107">Description</span></span>  
 <span data-ttu-id="5dc62-108">В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений которых являются производными от типа возвращаемого значения в сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="5dc62-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="5dc62-109">Тип данных, возвращаемый `DogsHandler`, является типом `Dogs`, производным от определенного в делегате типа `Mammals`.</span><span class="sxs-lookup"><span data-stu-id="5dc62-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5dc62-110">Код</span><span class="sxs-lookup"><span data-stu-id="5dc62-110">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="5dc62-111">Пример 2. Контравариантность</span><span class="sxs-lookup"><span data-stu-id="5dc62-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="5dc62-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="5dc62-112">Description</span></span>

<span data-ttu-id="5dc62-113">В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра сигнатуры делегата.</span><span class="sxs-lookup"><span data-stu-id="5dc62-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="5dc62-114">Контравариантность позволяет использовать один обработчик событий вместо нескольких.</span><span class="sxs-lookup"><span data-stu-id="5dc62-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="5dc62-115">В следующем примере используется два делегата:</span><span class="sxs-lookup"><span data-stu-id="5dc62-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="5dc62-116">Делегат <xref:System.Windows.Forms.KeyEventHandler>, определяющий сигнатуру события [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="5dc62-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="5dc62-117">Его сигнатура:</span><span class="sxs-lookup"><span data-stu-id="5dc62-117">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="5dc62-118">Делегат <xref:System.Windows.Forms.MouseEventHandler>, определяющий сигнатуру события [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="5dc62-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="5dc62-119">Его сигнатура:</span><span class="sxs-lookup"><span data-stu-id="5dc62-119">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="5dc62-120">В примере определяется обработчик событий с параметром <xref:System.EventArgs>, который используется для обработки событий `Button.KeyDown` и `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="5dc62-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="5dc62-121">Это можно сделать, поскольку <xref:System.EventArgs> является базовым типом <xref:System.Windows.Forms.KeyEventArgs> и <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="5dc62-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="5dc62-122">Код</span><span class="sxs-lookup"><span data-stu-id="5dc62-122">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dc62-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5dc62-123">See also</span></span>

- [<span data-ttu-id="5dc62-124">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="5dc62-124">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="5dc62-125">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="5dc62-125">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
