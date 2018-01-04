---
title: "Практическое руководство. Удаление данных рукописного ввода в настраиваемом элементе управления"
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
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e05163bcbafd360e0929fe784ff1111bd0663ef3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Практическое руководство. Удаление данных рукописного ввода в настраиваемом элементе управления
<xref:System.Windows.Ink.IncrementalStrokeHitTester> Определяет, пересекается ли текущий росчерк stroke в другой.  Это полезно для создания элемента управления, который позволяет пользователю стирать части штриха, способ пользователь может выполнять на <xref:System.Windows.Controls.InkCanvas> при <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> равно <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается пользовательский элемент управления, который позволяет пользователю стирать части росчерков.  В этом примере создается элемент управления, содержащий рукописного ввода при ее инициализации.  Создание элемента управления, который собирает рукописного ввода — [создания элемента управления ввода рукописного ввода](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
