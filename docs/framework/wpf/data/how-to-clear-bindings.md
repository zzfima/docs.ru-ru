---
title: Практическое руководство. Очистка привязок
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 66f7eb0209d23660b9c7351ca793f509b2f4bb8d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458878"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="595b0-102">Практическое руководство. Очистка привязок</span><span class="sxs-lookup"><span data-stu-id="595b0-102">How to: Clear Bindings</span></span>
<span data-ttu-id="595b0-103">В этом примере показано, как удалять привязки к объекту.</span><span class="sxs-lookup"><span data-stu-id="595b0-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="595b0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="595b0-104">Example</span></span>  
 <span data-ttu-id="595b0-105">Чтобы удалить привязку из отдельного свойства объекта, вызовите <xref:System.Windows.Data.BindingOperations.ClearBinding%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="595b0-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="595b0-106">В следующем примере удаляется привязка из <xref:System.Windows.Controls.TextBlock.TextProperty> *myText*, объекта <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="595b0-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="595b0-107">Очистка привязки удаляет привязку так, что значение свойства зависимостей изменяется на то значение, которое было бы без привязки.</span><span class="sxs-lookup"><span data-stu-id="595b0-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="595b0-108">Это значение может быть значением по умолчанию, унаследованным или значением из привязки шаблона данных.</span><span class="sxs-lookup"><span data-stu-id="595b0-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="595b0-109">Чтобы очистить привязки от всех возможных свойств объекта, используйте <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="595b0-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595b0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="595b0-110">See also</span></span>

- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="595b0-111">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="595b0-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="595b0-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="595b0-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
