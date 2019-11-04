---
title: Практическое руководство. Создать простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453512"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="cce92-102">Практическое руководство. Создать простой привязки</span><span class="sxs-lookup"><span data-stu-id="cce92-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="cce92-103">В этом примере показано, как создать простой <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="cce92-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cce92-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cce92-104">Example</span></span>  
 <span data-ttu-id="cce92-105">В этом примере имеется объект `Person` со строковым свойством с именем `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="cce92-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="cce92-106">Объект `Person` определен в пространстве имен с именем `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="cce92-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="cce92-107">Выделенная строка, содержащая элемент `<src>` в следующем примере, создает объект `Person` со значением свойства `PersonName` `Joe`.</span><span class="sxs-lookup"><span data-stu-id="cce92-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="cce92-108">Это делается в разделе `Resources` и назначается `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="cce92-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="cce92-109">Выделенная строка, содержащая элемент `<TextBlock>`, привязывает элемент управления <xref:System.Windows.Controls.TextBlock> к свойству `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="cce92-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="cce92-110">В результате <xref:System.Windows.Controls.TextBlock> отображается со значением Joe.</span><span class="sxs-lookup"><span data-stu-id="cce92-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce92-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cce92-111">See also</span></span>

- [<span data-ttu-id="cce92-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="cce92-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cce92-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="cce92-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
