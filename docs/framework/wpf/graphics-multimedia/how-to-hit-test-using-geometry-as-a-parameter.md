---
title: Практическое руководство. Проверка нажатия с использованием геометрии в качестве параметра
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923406"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Практическое руководство. Проверка нажатия с использованием геометрии в качестве параметра
В этом примере показано, как выполнить проверку нажатия для визуального объекта, <xref:System.Windows.Media.Geometry> используя в качестве параметра проверки нажатия.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить проверку нажатия с помощью <xref:System.Windows.Media.GeometryHitTestParameters> <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метода. Значение, передаваемое `OnMouseDown` в метод <xref:System.Windows.Media.Geometry> , используется для создания объекта, чтобы расширить диапазон проверки нажатия. <xref:System.Windows.Point>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Свойство объекта <xref:System.Windows.Media.GeometryHitTestResult> предоставляет сведения о результатах проверки попадания, которая использует в <xref:System.Windows.Media.Geometry> качестве параметра проверки нажатия. <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> На следующем рисунке показана связь между геометрическим объектом проверки нажатия (синий круг) и отображенным содержимым целевого визуального объекта (красный квадрат).  
  
 ![Схема, на которой показаны IntersectionDetail, используемые при проверке попадания.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 В следующем примере показано, как реализовать обратный вызов проверки попадания при <xref:System.Windows.Media.Geometry> использовании в качестве параметра проверки нажатия. Параметр приводится к типу, <xref:System.Windows.Media.GeometryHitTestResult> чтобы <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> получить значение свойства. `result` Значение свойства позволяет определить, является ли <xref:System.Windows.Media.Geometry> параметр проверки нажатия полностью или частично включен в отображаемое содержимое целевого объекта проверки попадания. В этом случае пример кода только добавляет результаты проверки попадания в список визуальных объектов, которые полностью содержатся в пределах границ целевого объекта.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> Обратный вызов не должен вызываться, если сведения о пересечении имеют <xref:System.Windows.Media.IntersectionDetail.Empty>значение. <xref:System.Windows.Media.HitTestResult>  
  
## <a name="see-also"></a>См. также

- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
- [Проверка попадания геометрического объекта в визуальный объект](how-to-hit-test-geometry-in-a-visual.md)
