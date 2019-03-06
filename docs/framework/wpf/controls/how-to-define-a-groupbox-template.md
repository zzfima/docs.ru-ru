---
title: Практическое руководство. Определение шаблона GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6b4ad4a588aab93f5445cda962af890bfcd41c14
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377668"
---
# <a name="how-to-define-a-groupbox-template"></a>Практическое руководство. Определение шаблона GroupBox
В этом примере показано, как создать шаблон для <xref:System.Windows.Controls.GroupBox> элемента управления.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется <xref:System.Windows.Controls.GroupBox> шаблона элемента управления с помощью <xref:System.Windows.Controls.Grid> управления для макета. В шаблоне используется <xref:System.Windows.Controls.BorderGapMaskConverter> для определения границ <xref:System.Windows.Controls.GroupBox> таким образом, чтобы границы не скрывать <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> содержимого.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.GroupBox>
- [Практическое руководство. Создание GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))
