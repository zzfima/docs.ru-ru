---
title: 'Как: окна сообщения'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: dd79d69c9b1b54c5158b58ee2f1675e7d11a386a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-message-box"></a>Как: окна сообщения
В этом примере показано, как открыть окно сообщения.  
  
## <a name="example"></a>Пример  
 Окно сообщения является готовое модальное диалоговое окно для отображения сведений для пользователей. Открывается окно сообщения путем вызова статического <xref:System.Windows.MessageBox.Show%2A> метод <xref:System.Windows.MessageBox> класса. Если <xref:System.Windows.MessageBox.Show%2A> является именем, сообщение передается с помощью параметра строки. Несколько перегрузок <xref:System.Windows.MessageBox.Show%2A> дают возможность настраивать, как отображается окно сообщения (в разделе <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>См. также  
 [Образец MessageBox](http://go.microsoft.com/fwlink/?LinkID=160023)
