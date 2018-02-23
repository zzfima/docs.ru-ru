---
title: "Практическое руководство. Создать простой привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a595f255b014e08b4b5b2036a7b1940e46df268f
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="84d41-102">Практическое руководство. Создать простой привязки</span><span class="sxs-lookup"><span data-stu-id="84d41-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="84d41-103">В этом примере показано, как создать простой <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="84d41-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84d41-104">Пример</span><span class="sxs-lookup"><span data-stu-id="84d41-104">Example</span></span>  
 <span data-ttu-id="84d41-105">В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="84d41-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="84d41-106">`Person` Объект определен в пространстве имен `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="84d41-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="84d41-107">Выделенная строка, содержащий `<src>` элемент в следующем примере создается экземпляр `Person` объекта с `PersonName` значение свойства `Joe`.</span><span class="sxs-lookup"><span data-stu-id="84d41-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="84d41-108">Это можно сделать в `Resources` статьи и назначены `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="84d41-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="84d41-109">Выделенная строка, содержащий `<TextBlock>` привязывается элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство.</span><span class="sxs-lookup"><span data-stu-id="84d41-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="84d41-110">В результате <xref:System.Windows.Controls.TextBlock> имеет значение «Joe».</span><span class="sxs-lookup"><span data-stu-id="84d41-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d41-111">См. также</span><span class="sxs-lookup"><span data-stu-id="84d41-111">See Also</span></span>  
 [<span data-ttu-id="84d41-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="84d41-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="84d41-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="84d41-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
