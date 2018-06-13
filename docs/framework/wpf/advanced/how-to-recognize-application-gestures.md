---
title: Практическое руководство. Распознавание жестов приложений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 82ca91fc9e3745012d82357991b67f398079f1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543697"
---
# <a name="how-to-recognize-application-gestures"></a>Практическое руководство. Распознавание жестов приложений
Следующий пример демонстрирует стирания рукописного ввода, когда пользователь делает <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> жестов на <xref:System.Windows.Controls.InkCanvas>. В этом примере предполагается <xref:System.Windows.Controls.InkCanvas>, который называется `inkCanvas1`, объявленных в файле XAML.  
  
## <a name="example"></a>Пример  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
