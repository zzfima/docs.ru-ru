---
title: Практическое руководство. Проверка нажатия в Viewport3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D visuals [WPF], hit-testing for
- hit tests [WPF], for 3D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 34bc86349332293e40aca5743cbabb2a48634da6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112093"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="77e36-102">Практическое руководство. Проверка нажатия в Viewport3D</span><span class="sxs-lookup"><span data-stu-id="77e36-102">How to: Hit Test in a Viewport3D</span></span>

<span data-ttu-id="77e36-103">Этот пример показывает, как попасть тест для <xref:System.Windows.Controls.Viewport3D>3D Визуальные эффекты в .</span><span class="sxs-lookup"><span data-stu-id="77e36-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>

<span data-ttu-id="77e36-104">Поскольку <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> возвращает 2D и 3D информацию, можно итерировать через результаты тестирования, чтобы прочитать только 3D результаты.</span><span class="sxs-lookup"><span data-stu-id="77e36-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

<span data-ttu-id="77e36-105">В <xref:System.Windows.Media.HitTestResultBehavior> следующем коде определяется, как обрабатываются результаты теста.</span><span class="sxs-lookup"><span data-stu-id="77e36-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span> <span data-ttu-id="77e36-106">`UpdateResultInfo`и `UpdateMaterial` являются локально определенными методами.</span><span class="sxs-lookup"><span data-stu-id="77e36-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
