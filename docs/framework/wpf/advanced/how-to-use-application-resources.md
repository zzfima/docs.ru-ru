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
# <a name="how-to-use-application-resources"></a>Практическое руководство. Использование ресурсов приложения
В этом примере показаны способы использования ресурсов приложения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показан файл определения приложения. В файле определения приложения определяет раздел ресурсов (значение <xref:System.Windows.Application.Resources%2A> свойства). Ресурсы, определенные на уровне приложения, могут быть доступны для всех остальных страниц, являющихся частью приложения. В этом случае ресурс является объявленным стилем. Поскольку полный стиль, содержащий шаблон элемента управления может быть длинным, в этом примере указывается шаблон элемента управления, в котором определен <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> метод задания свойства стиля.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницу, которая ссылается на ресурс на уровне приложения, определенные в предыдущем примере. Ресурс указывается с помощью [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) , задающий уникальный ключ ресурса для запрошенного ресурса. На текущей странице не найдено ресурса с ключом GelButton, поэтому область поиска ресурса для запрошенного ресурса продолжается за пределами текущей страницы в ресурсах, определенных на уровне приложения.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
