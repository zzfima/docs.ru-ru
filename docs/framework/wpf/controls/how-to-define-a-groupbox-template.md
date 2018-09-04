---
title: Практическое руководство. Определение шаблона GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: a47ce896be4d1c38147584dd80b1bc841737d526
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43537389"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="8163e-102">Практическое руководство. Определение шаблона GroupBox</span><span class="sxs-lookup"><span data-stu-id="8163e-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="8163e-103">В этом примере показано, как создать шаблон для <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8163e-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8163e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8163e-104">Example</span></span>  
 <span data-ttu-id="8163e-105">В следующем примере определяется <xref:System.Windows.Controls.GroupBox> шаблона элемента управления с помощью <xref:System.Windows.Controls.Grid> управления для макета.</span><span class="sxs-lookup"><span data-stu-id="8163e-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="8163e-106">В шаблоне используется <xref:System.Windows.Controls.BorderGapMaskConverter> для определения границ <xref:System.Windows.Controls.GroupBox> таким образом, чтобы границы не скрывать <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> содержимого.</span><span class="sxs-lookup"><span data-stu-id="8163e-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="8163e-107">См. также</span><span class="sxs-lookup"><span data-stu-id="8163e-107">See Also</span></span>  
 <xref:System.Windows.Controls.GroupBox>  
 [<span data-ttu-id="8163e-108">Разделы руководства, посвященные GroupBox</span><span class="sxs-lookup"><span data-stu-id="8163e-108">GroupBox How-to Topics</span></span>](https://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
