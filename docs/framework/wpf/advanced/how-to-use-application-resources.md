---
title: "Практическое руководство. Использование ресурсов приложения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ресурсы приложений"
  - "ресурсы, ресурсы приложений"
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Использование ресурсов приложения
В этом примере показаны способы использования ресурсов приложения.  
  
## Пример  
 В следующем примере показан файл определения приложения.  Файл определения приложения определяет раздел ресурсов \(значение свойства <xref:System.Windows.Application.Resources%2A>\).  Ресурсы, определенные на уровне приложения, могут быть доступны для всех остальных страниц, являющихся частью приложения.  В этом случае ресурс является объявленным стилем.  Поскольку полный стиль, содержащий шаблон элемента управления, может быть длинным, в этом примере шаблон элемента управления, заданный в механизме установки свойства <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> стиля, опускается.  
  
 [!code-xml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 В следующем примере показана страница [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которая ссылается на ресурс на уровне приложения, заданный в предыдущем примере.  Ссылка на ресурс указывается с помощью [Расширение разметки StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md), который задает уникальный ключ ресурса для запрошенного ресурса.  На текущей странице не найдено ресурса с ключом «GelButton», поэтому область поиска ресурса для запрошенного ресурса продолжается за пределами текущей страницы и в ресурсах, определенных на уровне приложения.  
  
 [!code-xml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## См. также  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)