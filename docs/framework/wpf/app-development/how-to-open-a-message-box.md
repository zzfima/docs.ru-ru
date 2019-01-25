---
title: Как выполнить Отображение окна сообщения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: 1bde7c4f794ca7e3b01490db8e918b06b5074bcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739736"
---
# <a name="how-to-open-a-message-box"></a>Как выполнить Отображение окна сообщения
В этом примере показано, как открыть окно сообщения.  
  
## <a name="example"></a>Пример  
 Окно сообщения — это готовое модальное диалоговое окно для отображения сведений для пользователей. Открывается окно сообщения путем вызова статического <xref:System.Windows.MessageBox.Show%2A> метод <xref:System.Windows.MessageBox> класса. Когда <xref:System.Windows.MessageBox.Show%2A> является именем, сообщение, передается с помощью параметра строки. Несколько перегрузок <xref:System.Windows.MessageBox.Show%2A> дают возможность настраивать, как будет выглядеть окно сообщения (см. в разделе <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>См. также
- [Пример MessageBox](https://go.microsoft.com/fwlink/?LinkID=160023)
