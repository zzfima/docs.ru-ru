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
ms.openlocfilehash: f66477fc857a9e7a065e01b8cddf43789042b59c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555861"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="5a2e7-102">Практическое руководство. Очистка привязок</span><span class="sxs-lookup"><span data-stu-id="5a2e7-102">How to: Clear Bindings</span></span>
<span data-ttu-id="5a2e7-103">В этом примере показано, как удалять привязки к объекту.</span><span class="sxs-lookup"><span data-stu-id="5a2e7-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a2e7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5a2e7-104">Example</span></span>  
 <span data-ttu-id="5a2e7-105">Чтобы удалить привязку из отдельного свойства объекта, вызовите <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5a2e7-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="5a2e7-106">Следующий пример удаляет привязку из <xref:System.Windows.Controls.TextBlock.TextProperty> из *mytext*, <xref:System.Windows.Controls.TextBlock> объекта.</span><span class="sxs-lookup"><span data-stu-id="5a2e7-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="5a2e7-107">Очистка привязки удаляет привязку так, что значение свойства зависимостей изменяется на то значение, которое было бы без привязки.</span><span class="sxs-lookup"><span data-stu-id="5a2e7-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="5a2e7-108">Это значение может быть значением по умолчанию, унаследованным или значением из привязки шаблона данных.</span><span class="sxs-lookup"><span data-stu-id="5a2e7-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="5a2e7-109">Чтобы очистить привязки от всех возможных свойств объекта, используйте <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a2e7-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2e7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5a2e7-110">See Also</span></span>  
 <xref:System.Windows.Data.BindingOperations>  
 [<span data-ttu-id="5a2e7-111">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="5a2e7-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="5a2e7-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="5a2e7-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
