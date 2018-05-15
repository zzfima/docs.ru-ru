---
title: Практическое руководство. Создать простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 8910dd3ec6c9f72f9d8fb64cd33912f0d4318e5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="e1e0d-102">Практическое руководство. Создать простой привязки</span><span class="sxs-lookup"><span data-stu-id="e1e0d-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="e1e0d-103">В этом примере показано, как создать простой <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e0d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e0d-104">Example</span></span>  
 <span data-ttu-id="e1e0d-105">В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="e1e0d-106">`Person` Объект определен в пространстве имен `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="e1e0d-107">Выделенная строка, содержащий `<src>` элемент в следующем примере создается экземпляр `Person` объекта с `PersonName` значение свойства `Joe`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="e1e0d-108">Это можно сделать в `Resources` статьи и назначены `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="e1e0d-109">Выделенная строка, содержащий `<TextBlock>` привязывается элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="e1e0d-110">В результате <xref:System.Windows.Controls.TextBlock> имеет значение «Joe».</span><span class="sxs-lookup"><span data-stu-id="e1e0d-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e0d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e0d-111">See Also</span></span>  
 [<span data-ttu-id="e1e0d-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="e1e0d-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e1e0d-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e1e0d-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
