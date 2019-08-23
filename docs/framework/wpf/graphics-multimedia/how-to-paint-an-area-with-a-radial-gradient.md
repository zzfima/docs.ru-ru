---
title: Практическое руководство. Заливка области с помощью радиального градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 5762ef1a1526ba6f004917c8a947e35ce731c86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916102"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Практическое руководство. Заливка области с помощью радиального градиента
В этом примере показано, как с <xref:System.Windows.Media.RadialGradientBrush> помощью класса закрасить область с радиальным градиентом.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.RadialGradientBrush> для рисования прямоугольника с радиальным градиентом, который переходит от желтого к красному к темному зеленому.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 На следующем рисунке показан градиент из предыдущего примера. Выделены точки останова градиента.  
  
 ![Ограничения градиента в радиальном градиенте](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
> В примерах этого раздела используется система координат по умолчанию для установки контрольных точек. Система координат по умолчанию относится к ограничивающему прямоугольнику: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 указывает 100 процентов ограничивающего прямоугольника. Вы можете изменить эту систему координат, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> для свойства значение. <xref:System.Windows.Media.BrushMappingMode.Absolute> Абсолютная система координат не привязана к ограничивающему прямоугольнику. Значения интерпретируются непосредственно в локальной области.  
  
 Дополнительные <xref:System.Windows.Media.RadialGradientBrush> примеры см. в [образце кистей](https://go.microsoft.com/fwlink/?LinkID=159973). Дополнительные сведения о градиентах и других типах кистей см. [в статье Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).
