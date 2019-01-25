---
title: 'Как выполнить: Распознавание жестов приложений'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 68a7c8cd4b8ed935d005fabff37a7b44c1b98012
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506710"
---
# <a name="how-to-recognize-application-gestures"></a>Как выполнить: Распознавание жестов приложений
Следующий пример демонстрирует удаление данных рукописного ввода, когда пользователь делает <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> жестов на <xref:System.Windows.Controls.InkCanvas>. В этом примере предполагается <xref:System.Windows.Controls.InkCanvas>, который называется `inkCanvas1`, объявляется в файле XAML.  
  
## <a name="example"></a>Пример  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
