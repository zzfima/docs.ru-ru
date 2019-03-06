---
title: Практическое руководство. Получение возвращаемого значения функции страницы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: fd54a5059d028f9fc6624d1e2d03b209140b481c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365143"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a><span data-ttu-id="3f13a-102">Практическое руководство. Получение возвращаемого значения функции страницы</span><span class="sxs-lookup"><span data-stu-id="3f13a-102">How to: Get the Return Value of a Page Function</span></span>
<span data-ttu-id="3f13a-103">В этом примере показано, как получить результат, возвращаемый функцией страницы.</span><span class="sxs-lookup"><span data-stu-id="3f13a-103">This example shows how to get the result that is returned by a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f13a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3f13a-104">Example</span></span>  
 <span data-ttu-id="3f13a-105">Чтобы получить результат, который возвращается из функции страницы, необходимо обрабатывать <xref:System.Windows.Navigation.PageFunction%601.Return> при вызове функции страницы.</span><span class="sxs-lookup"><span data-stu-id="3f13a-105">To get the result that is returned from a page function, you need to handle <xref:System.Windows.Navigation.PageFunction%601.Return> of the page function you are calling.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="3f13a-106">См. также</span><span class="sxs-lookup"><span data-stu-id="3f13a-106">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
