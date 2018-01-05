---
title: "Практическое руководство. Очистка привязок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af45d504eb4e7d45808f787925a90c8e0ed19476
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="08426-102">Практическое руководство. Очистка привязок</span><span class="sxs-lookup"><span data-stu-id="08426-102">How to: Clear Bindings</span></span>
<span data-ttu-id="08426-103">В этом примере показано, как удалять привязки к объекту.</span><span class="sxs-lookup"><span data-stu-id="08426-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08426-104">Пример</span><span class="sxs-lookup"><span data-stu-id="08426-104">Example</span></span>  
 <span data-ttu-id="08426-105">Чтобы удалить привязку из отдельного свойства объекта, вызовите <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="08426-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="08426-106">Следующий пример удаляет привязку из <xref:System.Windows.Controls.TextBlock.TextProperty> из *mytext*, <xref:System.Windows.Controls.TextBlock> объекта.</span><span class="sxs-lookup"><span data-stu-id="08426-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="08426-107">Очистка привязки удаляет привязку так, что значение свойства зависимостей изменяется на то значение, которое было бы без привязки.</span><span class="sxs-lookup"><span data-stu-id="08426-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="08426-108">Это значение может быть значением по умолчанию, унаследованным или значением из привязки шаблона данных.</span><span class="sxs-lookup"><span data-stu-id="08426-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="08426-109">Чтобы очистить привязки от всех возможных свойств объекта, используйте <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="08426-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08426-110">См. также</span><span class="sxs-lookup"><span data-stu-id="08426-110">See Also</span></span>  
 <xref:System.Windows.Data.BindingOperations>  
 [<span data-ttu-id="08426-111">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="08426-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="08426-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="08426-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
