---
title: Руководство по программированию на C#. Публикация событий, соответствующих рекомендациям .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 0ae240d0c078b5eaa690f128c037ee2471325872
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705344"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="d8757-102">Руководство по программированию на C#. Публикация событий, соответствующих рекомендациям .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d8757-102">How to publish events that conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="d8757-103">Следующая процедура показывает, как добавлять события, которые соответствуют стандартному шаблону .NET Framework для классов и структур.</span><span class="sxs-lookup"><span data-stu-id="d8757-103">The following procedure demonstrates how to add events that follow the standard .NET Framework pattern to your classes and structs.</span></span> <span data-ttu-id="d8757-104">Все события в библиотеке классов .NET Framework основаны на делегате <xref:System.EventHandler>, который определен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d8757-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
> <span data-ttu-id="d8757-105">В .NET Framework 2.0 представлена универсальная версия этого делегата, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="d8757-105">The .NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="d8757-106">В следующих примерах демонстрируется использование обеих версий.</span><span class="sxs-lookup"><span data-stu-id="d8757-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="d8757-107">Хотя события в определяемых классах могут быть основаны на действительном типе делегата, даже на делегатах, возвращающих значение, обычно рекомендуется основывать события на шаблоне .NET Framework с помощью <xref:System.EventHandler>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d8757-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET Framework pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="d8757-108">Публикация событий, основанных на шаблоне EventHandler</span><span class="sxs-lookup"><span data-stu-id="d8757-108">To publish events based on the EventHandler pattern</span></span>  
  
1. <span data-ttu-id="d8757-109">(Пропустите этот шаг и перейдите к шагу 3a, если не нужно отправлять пользовательские данные с определенным событием.) Объявите класс для пользовательских данных в области, видимой для классов Publisher и Subscriber.</span><span class="sxs-lookup"><span data-stu-id="d8757-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="d8757-110">Затем добавьте необходимые члены для хранения пользовательских данных о событиях.</span><span class="sxs-lookup"><span data-stu-id="d8757-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="d8757-111">В этом примере возвращается простая строка.</span><span class="sxs-lookup"><span data-stu-id="d8757-111">In this example, a simple string is returned.</span></span>  
  
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
  
2. <span data-ttu-id="d8757-112">(Пропустите этот шаг, если используется универсальная версия <xref:System.EventHandler%601>.) Объявите делегат в своем классе публикации.</span><span class="sxs-lookup"><span data-stu-id="d8757-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="d8757-113">Присвойте ему имя, которое заканчивается на *EventHandler*.</span><span class="sxs-lookup"><span data-stu-id="d8757-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="d8757-114">Второй параметр указывает настраиваемый тип EventArgs.</span><span class="sxs-lookup"><span data-stu-id="d8757-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3. <span data-ttu-id="d8757-115">Объявите событие в своем классе публикации, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d8757-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1. <span data-ttu-id="d8757-116">Если у вас нет пользовательского класса EventArgs, тип события будет неуниверсальным делегатом EventHandler.</span><span class="sxs-lookup"><span data-stu-id="d8757-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="d8757-117">Нет необходимости объявлять делегат, так как он уже объявлен в пространстве имен <xref:System>, которое включается при создании проекта C#.</span><span class="sxs-lookup"><span data-stu-id="d8757-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="d8757-118">Добавьте следующий код в класс Publisher.</span><span class="sxs-lookup"><span data-stu-id="d8757-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2. <span data-ttu-id="d8757-119">Если вы используете неуниверсальную версию <xref:System.EventHandler> и имеется пользовательский класс, производный от <xref:System.EventArgs>, объявите событие внутри класса публикации и используйте делегат из шага 2 в качестве типа.</span><span class="sxs-lookup"><span data-stu-id="d8757-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3. <span data-ttu-id="d8757-120">Если используется универсальная версия, пользовательский делегат не требуется.</span><span class="sxs-lookup"><span data-stu-id="d8757-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="d8757-121">Вместо этого в классе публикации укажите тип события как `EventHandler<CustomEventArgs>`, подставив имя своего класса в угловые скобки.</span><span class="sxs-lookup"><span data-stu-id="d8757-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="d8757-122">Пример</span><span class="sxs-lookup"><span data-stu-id="d8757-122">Example</span></span>  
 <span data-ttu-id="d8757-123">В следующем примере показана вышеописанная процедура с использованием пользовательского класса EventArgs и <xref:System.EventHandler%601> в качестве типа событий.</span><span class="sxs-lookup"><span data-stu-id="d8757-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d8757-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d8757-124">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="d8757-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d8757-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d8757-126">События</span><span class="sxs-lookup"><span data-stu-id="d8757-126">Events</span></span>](./index.md)
- [<span data-ttu-id="d8757-127">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d8757-127">Delegates</span></span>](../delegates/index.md)
