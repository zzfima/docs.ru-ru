---
title: Практическое руководство. Использование ресурсов приложения
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 8712f7c9c60d43cf3d0348b7c3f2f4cbee0b93b1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378890"
---
# <a name="how-to-use-application-resources"></a>Практическое руководство. Использование ресурсов приложения
В этом примере показаны способы использования ресурсов приложения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показан файл определения приложения. В файле определения приложения определяет раздел ресурсов (значение <xref:System.Windows.Application.Resources%2A> свойства). Ресурсы, определенные на уровне приложения, могут быть доступны для всех остальных страниц, являющихся частью приложения. В этом случае ресурс является объявленным стилем. Так как полный стиль, содержащий шаблон элемента управления может быть длинным, в этом примере пропускаются шаблон элемента управления, в котором определен <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> метода задания свойства стиля.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 В следующем примере показан [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницу, которая ссылается на ресурс уровня приложения, который определен в предыдущем примере. Ресурс указывается с помощью [расширение разметки StaticResource](staticresource-markup-extension.md) , указывающий уникальный ключ ресурса для запрошенного ресурса. На текущей странице не найдено ресурса с ключом GelButton, поэтому область поиска ресурса для запрошенного ресурса продолжается за пределами текущей страницы в ресурсах, определенных на уровне приложения.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>См. также
- [Ресурсы XAML](xaml-resources.md)
- [Общие сведения об управлении приложением](../app-development/application-management-overview.md)
- [Разделы практического руководства](resources-how-to-topics.md)
