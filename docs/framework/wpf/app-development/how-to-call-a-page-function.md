---
title: "Практическое руководство. Вызов функции страницы"
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
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba1aa9c713d311bf1c6b42e8f72e89bb292927dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="bd4c6-102">Практическое руководство. Вызов функции страницы</span><span class="sxs-lookup"><span data-stu-id="bd4c6-102">How to: Call a Page Function</span></span>
<span data-ttu-id="bd4c6-103">В этом примере показано, как вызвать функцию страницы из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="bd4c6-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd4c6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bd4c6-104">Example</span></span>  
 <span data-ttu-id="bd4c6-105">Можно перейти к странице функции с помощью [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], так же, как при переходе на страницу.</span><span class="sxs-lookup"><span data-stu-id="bd4c6-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="bd4c6-106">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bd4c6-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="bd4c6-107">Если необходимо передать данные в функцию страницы, можно создать ее экземпляр и передать данные путем установки свойства.</span><span class="sxs-lookup"><span data-stu-id="bd4c6-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="bd4c6-108">Кроме того, можно передать данные с помощью конструктора не по умолчанию, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bd4c6-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="bd4c6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="bd4c6-109">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
