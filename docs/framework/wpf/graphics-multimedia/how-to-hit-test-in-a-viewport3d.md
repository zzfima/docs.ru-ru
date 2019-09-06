---
title: Практическое руководство. Проверка нажатия в Viewport3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 6eb68f4668c6ea5aa8728a81fac98409896f3fd2
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373272"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Практическое руководство. Проверка нажатия в Viewport3D

В этом примере показано, как выполнить проверку нажатия для трехмерных <xref:System.Windows.Controls.Viewport3D>визуальных элементов в.

Поскольку <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> возвращает данные 2D и 3D, можно выполнить итерацию по результатам теста, чтобы считывать только объемные результаты.

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

<xref:System.Windows.Media.HitTestResultBehavior> В следующем коде определяется, как обрабатываются результаты проверки попадания. `UpdateResultInfo`и `UpdateMaterial` — это локально определенные методы.

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
