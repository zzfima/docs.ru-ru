---
title: Практическое руководство. Возврат из функции страницы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- returning from page functions [WPF]
- page functions [WPF], returning from
- functions [WPF], returning from
ms.assetid: 87804905-7e8f-417b-b0e3-5622da686396
ms.openlocfilehash: 60e1d9d96104a9f4160280ba7208b7fe3680c1c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361048"
---
# <a name="how-to-return-from-a-page-function"></a>Практическое руководство. Возврат из функции страницы
В этом примере демонстрируется возврат результата из функции страницы.  
  
## <a name="example"></a>Пример  
 Чтобы вернуть из функции страницы, необходимо вызвать <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> и передать экземпляр <xref:System.Windows.Navigation.ReturnEventArgs%601>.  
  
 [!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml1)]  
[!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml2)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml.cs#pagefunctionreturnaresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/GetStringPageFunction.xaml.vb#pagefunctionreturnaresultcodebehind)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Navigation.PageFunction%601>
