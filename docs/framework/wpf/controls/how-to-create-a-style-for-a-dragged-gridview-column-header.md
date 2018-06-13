---
title: Как создать стиль для перетаскиваемого заголовка столбца GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: 2e57b4cb1b8ddb90e8e6e0abc6db3e7f0b864cfa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554577"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Как создать стиль для перетаскиваемого заголовка столбца GridView
В этом примере показано, как изменить внешний вид перетаскиваемого <xref:System.Windows.Controls.GridViewColumnHeader> когда пользователь изменяет положение столбца.  
  
## <a name="example"></a>Пример  
 Если перетащить заголовок столбца в другое место <xref:System.Windows.Controls.ListView> , использующий <xref:System.Windows.Controls.GridView> для режима просмотра, столбец перемещается на новое место. При перетаскивании заголовка столбца, перемещаемая копия заголовка возникает вместе с исходного заголовка. Заголовок столбца в <xref:System.Windows.Controls.GridView> представленного <xref:System.Windows.Controls.GridViewColumnHeader> объекта.  
  
 Чтобы настроить внешний вид перемещаемого и исходного заголовка, можно задать <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> изменить <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>. Эти <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> применяются при <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> значение свойства `true` и <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> значение свойства <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Когда пользователь нажимает кнопку мыши и удерживании его, когда указатель мыши задерживается на <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> примет значение свойства `true`. Аналогичным образом, в том случае, когда пользователь начинает операцию перетаскивания, <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> изменения свойств <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Следующий пример показывает, как задать <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> изменение <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.Background%2A> цвета заголовков исходного и с плавающей запятой при перетаскивании столбец в новое место.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
