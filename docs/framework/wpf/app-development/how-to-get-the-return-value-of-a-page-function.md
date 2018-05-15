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
ms.openlocfilehash: 2994a0fd7a192716a829c8290f030788da74cec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a><span data-ttu-id="6637d-102">Практическое руководство. Получение возвращаемого значения функции страницы</span><span class="sxs-lookup"><span data-stu-id="6637d-102">How to: Get the Return Value of a Page Function</span></span>
<span data-ttu-id="6637d-103">В этом примере показано, как получить результат, возвращаемый функцией страницы.</span><span class="sxs-lookup"><span data-stu-id="6637d-103">This example shows how to get the result that is returned by a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6637d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6637d-104">Example</span></span>  
 <span data-ttu-id="6637d-105">Чтобы получить результат, который возвращается из функции страницы, необходимо обработать <xref:System.Windows.Navigation.PageFunction%601.Return> вызова функции страницы.</span><span class="sxs-lookup"><span data-stu-id="6637d-105">To get the result that is returned from a page function, you need to handle <xref:System.Windows.Navigation.PageFunction%601.Return> of the page function you are calling.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="6637d-106">См. также</span><span class="sxs-lookup"><span data-stu-id="6637d-106">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
