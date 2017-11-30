---
title: "Практическое руководство. Нахождение элемента по его имени"
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
helpviewer_keywords: elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62e5cc9c65afe9da9c77d06c103e99d3ff8d995a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="cca43-102">Практическое руководство. Нахождение элемента по его имени</span><span class="sxs-lookup"><span data-stu-id="cca43-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="cca43-103">В этом примере описывается использование <xref:System.Windows.FrameworkElement.FindName%2A> метод, чтобы найти элемент по его <xref:System.Windows.FrameworkElement.Name%2A> значение.</span><span class="sxs-lookup"><span data-stu-id="cca43-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca43-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cca43-104">Example</span></span>  
 <span data-ttu-id="cca43-105">В этом примере обработчик событий кнопки представляет собой способ поиска определенного элемента по его имени.</span><span class="sxs-lookup"><span data-stu-id="cca43-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="cca43-106">`stackPanel`— <xref:System.Windows.FrameworkElement.Name%2A> корневого <xref:System.Windows.FrameworkElement> которой выполняется поиск, и метод примере затем визуально указывает найденный элемент, приводя его <xref:System.Windows.Controls.TextBlock> и изменение одного из <xref:System.Windows.Controls.TextBlock> видимым [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] свойства.</span><span class="sxs-lookup"><span data-stu-id="cca43-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
