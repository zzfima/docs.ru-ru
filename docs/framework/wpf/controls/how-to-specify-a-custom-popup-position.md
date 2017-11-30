---
title: "Практическое руководство. Указание пользовательского расположения контекстного меню"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ab9baca1103adf8de96204bdb1b3353a5456b94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a>Практическое руководство. Указание пользовательского расположения контекстного меню
В этом примере показано, как задать пользовательское позиционирование для <xref:System.Windows.Controls.Primitives.Popup> управления <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойству <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Пример  
 Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойству <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> вызывает определенный экземпляр <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегата. Этот делегат возвращает набор возможных точек относительно верхнего левого угла области назначения и в верхнем левом углу <xref:System.Windows.Controls.Primitives.Popup>. <xref:System.Windows.Controls.Primitives.Popup> Размещения происходит в точке, обеспечивающей наилучшую видимость.  
  
 В следующем примере показано, как определить положение <xref:System.Windows.Controls.Primitives.Popup> , установив <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Также показано, как создать и назначить <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат для расположения <xref:System.Windows.Controls.Primitives.Popup>.  Делегат обратного вызова возвращает два <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> объектов.  Если <xref:System.Windows.Controls.Primitives.Popup> по краю экрана на позицию первой скрыто <xref:System.Windows.Controls.Primitives.Popup> помещается во второй позиции.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Полный пример см. в разделе [пример размещения контекстного меню](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Общие сведения о контекстном меню](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
