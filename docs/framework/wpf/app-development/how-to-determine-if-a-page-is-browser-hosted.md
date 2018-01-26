---
title: "Как: определить страница в браузере"
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
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd8a8b8c3bea291afbe41e0c36e0d708bff3ef57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Как: определить страница в браузере
В этом примере показано, как определить <xref:System.Windows.Controls.Page> размещается в браузере.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Controls.Page> может размещаться независимо и, следовательно, может быть загружена в несколько различных типов узлов, включая <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, или в браузере. Это может произойти, если имеется библиотечная сборка, содержащий одну или несколько страниц, на который ссылаются несколько автономных и для просмотра ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) размещения приложений.  
  
 В следующем примере демонстрируется использование <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> ли <xref:System.Windows.Controls.Page> размещается в браузере.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
