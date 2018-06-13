---
title: Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 0bc793d4c95f8919517a83e434cf795e971dcd32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556735"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="6dd6a-102">Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки</span><span class="sxs-lookup"><span data-stu-id="6dd6a-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="6dd6a-103">В этом примере показано, как получить объект привязки из свойства целевого связанного объекта.</span><span class="sxs-lookup"><span data-stu-id="6dd6a-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dd6a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6dd6a-104">Example</span></span>  
 <span data-ttu-id="6dd6a-105">Необходимо выполнить следующую команду, чтобы получить <xref:System.Windows.Data.Binding> объекта:</span><span class="sxs-lookup"><span data-stu-id="6dd6a-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="6dd6a-106">Необходимо указать свойство зависимости для необходимой привязки, поскольку возможно, что привязка данных используется в нескольких (а не в одном) свойствах целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="6dd6a-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="6dd6a-107">Кроме того, можно получить <xref:System.Windows.Data.BindingExpression> , а затем получите значение <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="6dd6a-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="6dd6a-108">Полный пример см. в разделе [Пример проверки привязки](http://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="6dd6a-108">For the complete example see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dd6a-109">Если привязкой является <xref:System.Windows.Data.MultiBinding>, используйте <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="6dd6a-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="6dd6a-110">Если это <xref:System.Windows.Data.PriorityBinding>, используйте <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="6dd6a-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="6dd6a-111">Если вы не уверены, ли целевое свойство связан с помощью <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, или <xref:System.Windows.Data.PriorityBinding>, можно использовать <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="6dd6a-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd6a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6dd6a-112">See Also</span></span>  
 [<span data-ttu-id="6dd6a-113">Создание привязки в коде</span><span class="sxs-lookup"><span data-stu-id="6dd6a-113">Create a Binding in Code</span></span>](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [<span data-ttu-id="6dd6a-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="6dd6a-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
