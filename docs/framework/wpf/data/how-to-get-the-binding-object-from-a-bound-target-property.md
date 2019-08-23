---
title: Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c7aacc2145ffe98ec7b58afb3b2e3dca151ef0ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965434"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="dc7fe-102">Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки</span><span class="sxs-lookup"><span data-stu-id="dc7fe-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="dc7fe-103">В этом примере показано, как получить объект привязки из свойства целевого связанного объекта.</span><span class="sxs-lookup"><span data-stu-id="dc7fe-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc7fe-104">Пример</span><span class="sxs-lookup"><span data-stu-id="dc7fe-104">Example</span></span>  
 <span data-ttu-id="dc7fe-105">Чтобы получить объект, <xref:System.Windows.Data.Binding> можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dc7fe-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
> <span data-ttu-id="dc7fe-106">Необходимо указать свойство зависимости для необходимой привязки, поскольку возможно, что привязка данных используется в нескольких (а не в одном) свойствах целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="dc7fe-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="dc7fe-107">Кроме того, можно получить <xref:System.Windows.Data.BindingExpression> и получить значение <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="dc7fe-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="dc7fe-108">Полный пример см. в разделе [Пример проверки привязки](https://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="dc7fe-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc7fe-109">Если привязка — <xref:System.Windows.Data.MultiBinding>, используйте <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc7fe-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="dc7fe-110">Если это <xref:System.Windows.Data.BindingOperations>,используйте.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. <xref:System.Windows.Data.PriorityBinding></span><span class="sxs-lookup"><span data-stu-id="dc7fe-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="dc7fe-111">Если вы не уверены, привязано ли целевое свойство, с <xref:System.Windows.Data.Binding>помощью <xref:System.Windows.Data.MultiBinding>, или <xref:System.Windows.Data.PriorityBinding>, можно использовать.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A> <xref:System.Windows.Data.BindingOperations></span><span class="sxs-lookup"><span data-stu-id="dc7fe-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc7fe-112">См. также</span><span class="sxs-lookup"><span data-stu-id="dc7fe-112">See also</span></span>

- [<span data-ttu-id="dc7fe-113">Создание привязки в коде</span><span class="sxs-lookup"><span data-stu-id="dc7fe-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="dc7fe-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="dc7fe-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
