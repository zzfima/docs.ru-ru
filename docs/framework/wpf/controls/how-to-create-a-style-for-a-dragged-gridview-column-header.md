---
title: "Как создать стиль для перетаскиваемого заголовка столбца GridView | Microsoft Docs"
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
  - "ListView - элементы управления, применение стилей"
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Как создать стиль для перетаскиваемого заголовка столбца GridView
Этот пример показывает, как изменить внешний вид перетаскиваемого объекта <xref:System.Windows.Controls.GridViewColumnHeader>, когда пользователь изменяет положение столбца.  
  
## Пример  
 При перетаскивании заголовка столбца в другое местоположение в объекте <xref:System.Windows.Controls.ListView>, который использует <xref:System.Windows.Controls.GridView> для своего режима просмотра, столбец перемещается на новое место.  При перетаскивании заголовка столбца, перемещаемая копия заголовка отображается дополнительно к исходному заголовку.  Заголовок столбца в объекте <xref:System.Windows.Controls.GridView> представлен объектом <xref:System.Windows.Controls.GridViewColumnHeader>.  
  
 Чтобы настроить внешний вид перемещаемого и исходного заголовка, можно задать значение <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> для изменения <xref:System.Windows.Style> объекта <xref:System.Windows.Controls.GridViewColumnHeader>.  Эти свойства <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> применяются, когда для свойства <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> установлено значение `true` и для свойства <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> — значение <xref:System.Windows.Controls.GridViewColumnHeaderRole>.  
  
 Когда пользователь нажимает кнопку мыши и удерживает ее, пока указатель мыши находится на объекте <xref:System.Windows.Controls.GridViewColumnHeader>, значение свойства <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> меняется на `true`.  Аналогичным образом, когда пользователь начинает операцию перетаскивания, свойство <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> изменяется на <xref:System.Windows.Controls.GridViewColumnHeaderRole>.  
  
 В следующем примере показано, как установить свойство <xref:System.Windows.Controls.ControlTemplate.Triggers%2A>, чтобы изменить цвета <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.Background%2A> исходного и перемещаемого заголовков, когда пользователь перетаскивает столбец на новое место.  
  
 [!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## См. также  
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)