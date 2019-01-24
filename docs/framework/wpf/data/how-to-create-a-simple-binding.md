---
title: Как выполнить Создание простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 3e38fa5fd1c7d0a635efd93de6ebe551f1eb1b82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594841"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="aae89-102">Как выполнить Создание простой привязки</span><span class="sxs-lookup"><span data-stu-id="aae89-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="aae89-103">В этом примере показано, как создать простое <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="aae89-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aae89-104">Пример</span><span class="sxs-lookup"><span data-stu-id="aae89-104">Example</span></span>  
 <span data-ttu-id="aae89-105">В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="aae89-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="aae89-106">`Person` Объект определен в пространстве имен `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="aae89-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="aae89-107">Выделенная строка, содержащий `<src>` элемента в следующем примере создается экземпляр `Person` со `PersonName` значение свойства `Joe`.</span><span class="sxs-lookup"><span data-stu-id="aae89-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="aae89-108">Это можно сделать в `Resources` раздела и назначенный `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="aae89-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="aae89-109">Выделенная строка, содержащий `<TextBlock>` затем привязывает элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство.</span><span class="sxs-lookup"><span data-stu-id="aae89-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="aae89-110">В результате <xref:System.Windows.Controls.TextBlock> отображается со значением «Joe».</span><span class="sxs-lookup"><span data-stu-id="aae89-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae89-111">См. также</span><span class="sxs-lookup"><span data-stu-id="aae89-111">See also</span></span>
- [<span data-ttu-id="aae89-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="aae89-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="aae89-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="aae89-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
