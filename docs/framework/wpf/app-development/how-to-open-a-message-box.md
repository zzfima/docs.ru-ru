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
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="3dd2e-102">Как открыть окно сообщения</span><span class="sxs-lookup"><span data-stu-id="3dd2e-102">How to: Open a Message Box</span></span>
<span data-ttu-id="3dd2e-103">В этом примере показано, как открыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="3dd2e-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dd2e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3dd2e-104">Example</span></span>  
 <span data-ttu-id="3dd2e-105">Окно сообщения представляет собой готовое модальное диалоговое окно для отображения сведений пользователям.</span><span class="sxs-lookup"><span data-stu-id="3dd2e-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="3dd2e-106">Окно сообщения открывается путем вызова статического метода <xref:System.Windows.MessageBox.Show%2A> класса <xref:System.Windows.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="3dd2e-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="3dd2e-107">При вызове <xref:System.Windows.MessageBox.Show%2A> сообщение передается с помощью строкового параметра.</span><span class="sxs-lookup"><span data-stu-id="3dd2e-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="3dd2e-108">Несколько перегрузок <xref:System.Windows.MessageBox.Show%2A> позволяют настроить отображение окна сообщения (см. <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="3dd2e-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="3dd2e-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3dd2e-109">See also</span></span>

- [<span data-ttu-id="3dd2e-110">Пример MessageBox</span><span class="sxs-lookup"><span data-stu-id="3dd2e-110">MessageBox Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
