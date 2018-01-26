---
title: "Практическое руководство. Как сделать UIElement прозрачным или полупрозрачным"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25245319c02ae376410d71afb7a1e56eda259e99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Практическое руководство. Как сделать UIElement прозрачным или полупрозрачным
В этом примере показано, как сделать <xref:System.Windows.UIElement> прозрачным или полупрозрачным. Чтобы сделать элемент прозрачным или полупрозрачным, задайте его <xref:System.Windows.UIElement.Opacity%2A> свойство. Значение `0.0` делает элемент полностью прозрачной, а значение `1.0` делает элемент полностью непрозрачным. Значение `0.5` делает элемент 50% непрозрачный и т. д. Элемент <xref:System.Windows.UIElement.Opacity%2A> равно `1.0` по умолчанию.  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.UIElement.Opacity%2A> кнопку, чтобы `0.25`, что делает ее и ее содержимое (в данном случае текст кнопки) на 25% непрозрачной.  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Если содержимое элемента имеют свой собственный <xref:System.Windows.UIElement.Opacity%2A> параметры, эти значения умножаются от содержащего элементы <xref:System.Windows.UIElement.Opacity%2A>.  
  
 В следующем примере задается кнопки <xref:System.Windows.UIElement.Opacity%2A> для `0.25`и <xref:System.Windows.UIElement.Opacity%2A> из <xref:System.Windows.Controls.Image> содержащегося в кнопку, чтобы `0.5`. В результате изображение отображается 12,5% непрозрачным: 0,25 * 0,5 = 0,125.  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Другой способ управления прозрачностью элемента является установка степени непрозрачности <xref:System.Windows.Media.Brush> которая рисует элемент. Такой подход позволяет выборочно изменения непрозрачности отдельных частей элемента и дает выигрыш в производительности по сравнению с использованием элемента <xref:System.Windows.UIElement.Opacity%2A> свойство. В следующем примере задается <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для рисования кнопки <xref:System.Windows.Controls.Control.Background%2A> равно `0.25`. В результате кисти фона — непрозрачный 25%, но его содержимое (текст кнопки) остаются 100% непрозрачным.  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 Можно также управлять прозрачностью отдельных цветов в кисти. Дополнительные сведения о цветах и кистях см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Пример, в котором показана анимация непрозрачности элемента см. в разделе [Анимация прозрачности элемента или кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
