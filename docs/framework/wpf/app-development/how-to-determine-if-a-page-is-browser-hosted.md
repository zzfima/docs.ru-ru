---
title: Как определить, размещена ли страница в браузере
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424694"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="3aac6-102">Как определить, размещена ли страница в браузере</span><span class="sxs-lookup"><span data-stu-id="3aac6-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="3aac6-103">В этом примере показано, как определить, размещается ли <xref:System.Windows.Controls.Page> в браузере.</span><span class="sxs-lookup"><span data-stu-id="3aac6-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3aac6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3aac6-104">Example</span></span>  
 <span data-ttu-id="3aac6-105"><xref:System.Windows.Controls.Page> может быть независимым от узла и, следовательно, может быть загружена на несколько различных типов узлов, включая <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>или браузер.</span><span class="sxs-lookup"><span data-stu-id="3aac6-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="3aac6-106">Это может произойти, если имеется сборка библиотеки, содержащая одну или несколько страниц, на которые ссылается несколько автономных и отображаемых (XBAP) хост-приложений.</span><span class="sxs-lookup"><span data-stu-id="3aac6-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="3aac6-107">В следующем примере показано, как использовать <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>, чтобы определить, размещается ли <xref:System.Windows.Controls.Page> в браузере.</span><span class="sxs-lookup"><span data-stu-id="3aac6-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="3aac6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3aac6-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
