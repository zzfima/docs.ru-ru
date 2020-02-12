---
title: Как открыть окно сообщения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123731"
---
# <a name="how-to-open-a-message-box"></a>Как открыть окно сообщения
В этом примере показано, как открыть окно сообщения.  
  
## <a name="example"></a>Пример  
 Окно сообщения представляет собой готовое модальное диалоговое окно для отображения сведений пользователям. Окно сообщения открывается путем вызова статического метода <xref:System.Windows.MessageBox.Show%2A> класса <xref:System.Windows.MessageBox>. При вызове <xref:System.Windows.MessageBox.Show%2A> сообщение передается с помощью строкового параметра. Несколько перегрузок <xref:System.Windows.MessageBox.Show%2A> позволяют настроить отображение окна сообщения (см. <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>См. также раздел

- [Пример MessageBox](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
