---
title: Практическое руководство. Создание простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094389"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="2b4f4-102">Практическое руководство. Создание простой привязки</span><span class="sxs-lookup"><span data-stu-id="2b4f4-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="2b4f4-103">В этом примере показано, как создать простое <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="2b4f4-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b4f4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2b4f4-104">Example</span></span>  
 <span data-ttu-id="2b4f4-105">В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="2b4f4-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="2b4f4-106">`Person` Объект определен в пространстве имен `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="2b4f4-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="2b4f4-107">Выделенная строка, содержащий `<src>` элемента в следующем примере создается экземпляр `Person` со `PersonName` значение свойства `Joe`.</span><span class="sxs-lookup"><span data-stu-id="2b4f4-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="2b4f4-108">Это можно сделать в `Resources` раздела и назначенный `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="2b4f4-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="2b4f4-109">Выделенная строка, содержащий `<TextBlock>` затем привязывает элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство.</span><span class="sxs-lookup"><span data-stu-id="2b4f4-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="2b4f4-110">В результате <xref:System.Windows.Controls.TextBlock> отображается со значением «Joe».</span><span class="sxs-lookup"><span data-stu-id="2b4f4-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4f4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2b4f4-111">See also</span></span>

- [<span data-ttu-id="2b4f4-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="2b4f4-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="2b4f4-113">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="2b4f4-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
