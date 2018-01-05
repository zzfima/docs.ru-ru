---
title: "Практическое руководство. Использование ресурсов приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bac1fa1576e684a4b10f00310c08e4e7101a5df0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="6a94e-102">Практическое руководство. Использование ресурсов приложения</span><span class="sxs-lookup"><span data-stu-id="6a94e-102">How to: Use Application Resources</span></span>
<span data-ttu-id="6a94e-103">В этом примере показаны способы использования ресурсов приложения.</span><span class="sxs-lookup"><span data-stu-id="6a94e-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a94e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6a94e-104">Example</span></span>  
 <span data-ttu-id="6a94e-105">В приведенном ниже примере показан файл определения приложения.</span><span class="sxs-lookup"><span data-stu-id="6a94e-105">The following example shows an application definition file.</span></span> <span data-ttu-id="6a94e-106">В файле определения приложения определяет раздел ресурсов (значение <xref:System.Windows.Application.Resources%2A> свойства).</span><span class="sxs-lookup"><span data-stu-id="6a94e-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="6a94e-107">Ресурсы, определенные на уровне приложения, могут быть доступны для всех остальных страниц, являющихся частью приложения.</span><span class="sxs-lookup"><span data-stu-id="6a94e-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="6a94e-108">В этом случае ресурс является объявленным стилем.</span><span class="sxs-lookup"><span data-stu-id="6a94e-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="6a94e-109">Поскольку полный стиль, содержащий шаблон элемента управления может быть длинным, в этом примере указывается шаблон элемента управления, в котором определен <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> метод задания свойства стиля.</span><span class="sxs-lookup"><span data-stu-id="6a94e-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="6a94e-110">В следующем примере показан [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницу, которая ссылается на ресурс на уровне приложения, определенные в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="6a94e-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="6a94e-111">Ресурс указывается с помощью [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) , задающий уникальный ключ ресурса для запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="6a94e-111">The resource is referenced by using a     [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="6a94e-112">На текущей странице не найдено ресурса с ключом GelButton, поэтому область поиска ресурса для запрошенного ресурса продолжается за пределами текущей страницы в ресурсах, определенных на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="6a94e-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="6a94e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6a94e-113">See Also</span></span>  
 [<span data-ttu-id="6a94e-114">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="6a94e-114">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="6a94e-115">Общие сведения об управлении приложением</span><span class="sxs-lookup"><span data-stu-id="6a94e-115">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [<span data-ttu-id="6a94e-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="6a94e-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
