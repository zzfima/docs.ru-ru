---
title: Практическое руководство. Использование ресурсов приложения
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: e4114466fa8016f8e31100d7a37038b0abfdccca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460268"
---
# <a name="how-to-use-application-resources"></a>Практическое руководство. Использование ресурсов приложения
В этом примере показаны способы использования ресурсов приложения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показан файл определения приложения. Файл определения приложения определяет раздел ресурсов (значение для свойства <xref:System.Windows.Application.Resources%2A>). Ресурсы, определенные на уровне приложения, могут быть доступны для всех остальных страниц, являющихся частью приложения. В этом случае ресурс является объявленным стилем. Поскольку полный стиль, включающий шаблон элемента управления, может быть длинным, в этом примере шаблон элемента управления, определенный в свойстве <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойства стиля, опускается.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 В следующем примере показана [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страница, которая ссылается на ресурс уровня приложения, определенный в предыдущем примере. Ссылка на ресурс осуществляется с помощью [расширения разметки StaticResource](staticresource-markup-extension.md) , которое указывает уникальный ключ ресурса для запрошенного ресурса. На текущей странице не найдено ресурса с ключом GelButton, поэтому область поиска ресурса для запрошенного ресурса продолжается за пределами текущей страницы в ресурсах, определенных на уровне приложения.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>См. также

- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Общие сведения об управлении приложением](../app-development/application-management-overview.md)
- [Разделы практического руководства](resources-how-to-topics.md)
