---
title: Практическое руководство. Указание пользовательского расположения контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635752"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Практическое руководство. Указание пользовательского расположения контекстного меню
В этом примере показано, как <xref:System.Windows.Controls.Primitives.Popup> указать <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> пользовательское <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>положение для элемента управления, когда свойство настроено на управление.  
  
## <a name="example"></a>Пример  
 Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойство настроено <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> <xref:System.Windows.Controls.Primitives.Popup> на, вызовы <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> определенного экземпляра делегата. Этот делегат возвращает набор возможных точек, которые по отношению к верхнему левому <xref:System.Windows.Controls.Primitives.Popup>углу целевой области и верхнему левому углу . Размещение <xref:System.Windows.Controls.Primitives.Popup> происходит в точке, которая обеспечивает лучшую видимость.  
  
 Ниже приводится следующий <xref:System.Windows.Controls.Primitives.Popup> пример, как определить <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> положение <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойства, установив свойство для . Он также показывает, как создать <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> и назначить <xref:System.Windows.Controls.Primitives.Popup>делегата для того, чтобы позиционировать .  Делегат обратного вызова <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> возвращает два объекта.  <xref:System.Windows.Controls.Primitives.Popup> Если он скрыт краем экрана в <xref:System.Windows.Controls.Primitives.Popup> первом положении, то он помещается на втором.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Для полного образца [см.](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Primitives.Popup>
- [Обзор всплывающих окно](popup-overview.md)
- [Как статьи](popup-how-to-topics.md)
