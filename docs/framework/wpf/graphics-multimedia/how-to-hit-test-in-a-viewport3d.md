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
# <a name="how-to-hit-test-in-a-viewport3d"></a>Практическое руководство. Проверка нажатия в Viewport3D

Этот пример показывает, как попасть тест для <xref:System.Windows.Controls.Viewport3D>3D Визуальные эффекты в .

Поскольку <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> возвращает 2D и 3D информацию, можно итерировать через результаты тестирования, чтобы прочитать только 3D результаты.

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

В <xref:System.Windows.Media.HitTestResultBehavior> следующем коде определяется, как обрабатываются результаты теста. `UpdateResultInfo`и `UpdateMaterial` являются локально определенными методами.

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
