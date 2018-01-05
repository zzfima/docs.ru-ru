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
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="afeb1-102">Как: определить страница в браузере</span><span class="sxs-lookup"><span data-stu-id="afeb1-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="afeb1-103">В этом примере показано, как определить <xref:System.Windows.Controls.Page> размещается в браузере.</span><span class="sxs-lookup"><span data-stu-id="afeb1-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afeb1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="afeb1-104">Example</span></span>  
 <span data-ttu-id="afeb1-105">Объект <xref:System.Windows.Controls.Page> может размещаться независимо и, следовательно, может быть загружена в несколько различных типов узлов, включая <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, или в браузере.</span><span class="sxs-lookup"><span data-stu-id="afeb1-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="afeb1-106">Это может произойти, если имеется библиотечная сборка, содержащий одну или несколько страниц, на который ссылаются несколько автономных и для просмотра ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) размещения приложений.</span><span class="sxs-lookup"><span data-stu-id="afeb1-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="afeb1-107">В следующем примере демонстрируется использование <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> ли <xref:System.Windows.Controls.Page> размещается в браузере.</span><span class="sxs-lookup"><span data-stu-id="afeb1-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="afeb1-108">См. также</span><span class="sxs-lookup"><span data-stu-id="afeb1-108">See Also</span></span>  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>
