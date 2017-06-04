---
title: "Практическое руководство. Отображение содержимого ListView с помощью GridView | Microsoft Docs"
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
  - "GridView, отображение содержимого ListView"
  - "ListView - элементы управления, отображение содержимого с помощью GridView"
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Отображение содержимого ListView с помощью GridView
В этом примере показано, как определить режим представления <xref:System.Windows.Controls.GridView> для элемента управления <xref:System.Windows.Controls.ListView>.  
  
## Пример  
 Можно определить режим представления <xref:System.Windows.Controls.GridView>, указав объекты <xref:System.Windows.Controls.GridViewColumn>.  В следующем примере показано, как определить объекты <xref:System.Windows.Controls.GridViewColumn>, привязанные к содержимому данных, заданному для элемента управления <xref:System.Windows.Controls.ListView>.  Этот пример <xref:System.Windows.Controls.GridView> задает три объекта <xref:System.Windows.Controls.GridViewColumn>, сопоставленные с полями `FirstName`, `LastName` и `EmployeeNumber` `EmployeeInfoDataSource`, который установлен в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> элемента управления <xref:System.Windows.Controls.ListView>.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующей иллюстрации показано, как будет выглядеть этот пример.  
  
 ![ListView с выводом GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
## См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)