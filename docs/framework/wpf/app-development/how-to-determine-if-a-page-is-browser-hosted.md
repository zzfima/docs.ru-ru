---
title: Практическое руководство. Определить страницу в браузере
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: ebc5612f059a6cf26f2568bbc08e705b4b3014c1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359995"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="3c7ff-102">Практическое руководство. Определить страницу в браузере</span><span class="sxs-lookup"><span data-stu-id="3c7ff-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="3c7ff-103">В этом примере показано, как определить, если <xref:System.Windows.Controls.Page> размещается в браузере.</span><span class="sxs-lookup"><span data-stu-id="3c7ff-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c7ff-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3c7ff-104">Example</span></span>  
 <span data-ttu-id="3c7ff-105">Объект <xref:System.Windows.Controls.Page> может размещаться независимо и, следовательно, может быть загружена в несколько различных типов узлов, включая <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, или другой браузер.</span><span class="sxs-lookup"><span data-stu-id="3c7ff-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="3c7ff-106">Это может произойти, если у вас есть библиотечная сборка, содержащий одну или несколько страниц, на который ссылаются несколько автономных и отображаемых в обозревателе ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) размещения приложений.</span><span class="sxs-lookup"><span data-stu-id="3c7ff-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="3c7ff-107">Следующий пример демонстрирует, как использовать <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> на предмет <xref:System.Windows.Controls.Page> размещается в браузере.</span><span class="sxs-lookup"><span data-stu-id="3c7ff-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="3c7ff-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3c7ff-108">See also</span></span>
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
