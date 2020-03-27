---
title: Практическое руководство. Указание пользовательского расположения контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344954"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Практическое руководство. Указание пользовательского расположения контекстного меню
В этом примере показано, как <xref:System.Windows.Controls.Primitives.Popup> указать <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> пользовательское <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>положение для элемента управления, когда свойство настроено на управление.  
  
## <a name="example"></a>Пример  
 Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойство настроено <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> <xref:System.Windows.Controls.Primitives.Popup> на, вызовы <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> определенного экземпляра делегата. Этот делегат возвращает набор возможных точек, которые по отношению к верхнему <xref:System.Windows.Controls.Primitives.Popup>левому углу целевой области и верхнему левому углу . Размещение <xref:System.Windows.Controls.Primitives.Popup> происходит в точке, которая обеспечивает лучшую видимость.  
  
 Ниже приводится следующий <xref:System.Windows.Controls.Primitives.Popup> пример, как определить <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> положение <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойства, установив свойство для . Он также показывает, как создать <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> и назначить <xref:System.Windows.Controls.Primitives.Popup>делегата для того, чтобы позиционировать .  Делегат обратного вызова <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> возвращает два объекта.  <xref:System.Windows.Controls.Primitives.Popup> Если он скрыт краем экрана в <xref:System.Windows.Controls.Primitives.Popup> первом положении, то он помещается на втором.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Для полного образца [см.](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Primitives.Popup>
- [Общие сведения о контекстном меню](popup-overview.md)
- [Практические руководства](popup-how-to-topics.md)
