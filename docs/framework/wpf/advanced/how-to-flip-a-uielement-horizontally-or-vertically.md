---
title: Как отразить объект UIElement по горизонтали или по вертикали
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 89dcf668f1fe361480dabdab227a35ea40c344a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544399"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>Как отразить объект UIElement по горизонтали или по вертикали
В этом примере показано, как использовать <xref:System.Windows.Media.ScaleTransform> отражение <xref:System.Windows.UIElement> горизонтально или вертикально. В этом примере <xref:System.Windows.Controls.Button> управления (тип <xref:System.Windows.UIElement>) Перевернутая путем применения <xref:System.Windows.Media.ScaleTransform> для его <xref:System.Windows.UIElement.RenderTransform%2A> свойство.  
  
## <a name="example"></a>Пример  
 Кнопка для отражения на следующем рисунке.  
  
 ![Кнопка без преобразования](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
Элементов пользовательского интерфейса, чтобы отразить  
  
 Ниже показан код, который создает кнопку.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>Пример  
 Чтобы отразить кнопку горизонтально, создайте <xref:System.Windows.Media.ScaleTransform> и задайте его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство в значение -1. Применить <xref:System.Windows.Media.ScaleTransform> на кнопку <xref:System.Windows.UIElement.RenderTransform%2A> свойство.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Кнопка, перевернута горизонтально &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
Кнопка после применения ScaleTransform  
  
## <a name="example"></a>Пример  
 Как видно из предыдущего рисунка, кнопка была отражена, но он был перемещен. Это так, как кнопка была отражена от верхнего левого угла. Чтобы отразить кнопку на месте, необходимо применить <xref:System.Windows.Media.ScaleTransform> к ее центру, но не его угла. Простой способ применения <xref:System.Windows.Media.ScaleTransform> к кнопкам центр — задать свойству кнопки <xref:System.Windows.UIElement.RenderTransformOrigin%2A> значение 0,5, 0,5.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Кнопка, перевернута горизонтально по центру](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
Кнопка с RenderTransformOrigin 0,5, 0,5  
  
## <a name="example"></a>Пример  
 Чтобы отразить кнопку по вертикали, задайте <xref:System.Windows.Media.ScaleTransform> объекта <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойство вместо его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Кнопка, перевернута вертикально по центру](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
По вертикали отраженных кнопки  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
