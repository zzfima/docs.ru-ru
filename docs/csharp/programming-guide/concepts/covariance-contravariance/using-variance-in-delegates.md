---
title: Использование вариативности в делегатах (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 00e11d4ce755c8c75b73023fec14d95ebc96b4fe
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595267"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="38b77-102">Использование вариативности в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="38b77-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="38b77-103">При назначении метода делегату *ковариация* и *контравариантость* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода.</span><span class="sxs-lookup"><span data-stu-id="38b77-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="38b77-104">Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в делегате.</span><span class="sxs-lookup"><span data-stu-id="38b77-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="38b77-105">Контравариантность позволяет использовать метод с типами параметров, степень наследования которых меньше, чем у типа делегата.</span><span class="sxs-lookup"><span data-stu-id="38b77-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="38b77-106">Пример 1. Ковариантность</span><span class="sxs-lookup"><span data-stu-id="38b77-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="38b77-107">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="38b77-107">Description</span></span>  
 <span data-ttu-id="38b77-108">В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений которых являются производными от типа возвращаемого значения в сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="38b77-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="38b77-109">Тип данных, возвращаемый `DogsHandler`, является типом `Dogs`, производным от определенного в делегате типа `Mammals`.</span><span class="sxs-lookup"><span data-stu-id="38b77-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="38b77-110">Код</span><span class="sxs-lookup"><span data-stu-id="38b77-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="38b77-111">Пример 2: Контрвариантность</span><span class="sxs-lookup"><span data-stu-id="38b77-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="38b77-112">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="38b77-112">Description</span></span>  
 <span data-ttu-id="38b77-113">В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра сигнатуры делегата.</span><span class="sxs-lookup"><span data-stu-id="38b77-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="38b77-114">Контравариантность позволяет использовать один обработчик событий вместо нескольких.</span><span class="sxs-lookup"><span data-stu-id="38b77-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="38b77-115">Например, можно создать обработчик событий, принимающих входной параметр `EventArgs`, и использовать его с событием `Button.MouseClick`, которое отправляет тип `MouseEventArgs` в качестве параметра, а также с событием `TextBox.KeyDown`, которое отправляет параметр `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="38b77-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="38b77-116">Код</span><span class="sxs-lookup"><span data-stu-id="38b77-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="38b77-117">См. также</span><span class="sxs-lookup"><span data-stu-id="38b77-117">See also</span></span>

- [<span data-ttu-id="38b77-118">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="38b77-118">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="38b77-119">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="38b77-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
