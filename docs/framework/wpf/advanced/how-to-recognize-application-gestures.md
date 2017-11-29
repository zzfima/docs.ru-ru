---
title: "Практическое руководство. Распознавание жестов приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24d9e4435362f5f87185d04f911caf76517a0de9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="f4afc-102">Практическое руководство. Распознавание жестов приложений</span><span class="sxs-lookup"><span data-stu-id="f4afc-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="f4afc-103">Следующий пример демонстрирует стирания рукописного ввода, когда пользователь делает <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> жестов на <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="f4afc-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="f4afc-104">В этом примере предполагается <xref:System.Windows.Controls.InkCanvas>, который называется `inkCanvas1`, объявленных в файле XAML.</span><span class="sxs-lookup"><span data-stu-id="f4afc-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4afc-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f4afc-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f4afc-106">См. также</span><span class="sxs-lookup"><span data-stu-id="f4afc-106">See Also</span></span>  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
