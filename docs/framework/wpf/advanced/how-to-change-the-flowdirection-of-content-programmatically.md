---
title: Как изменить FlowDirection содержимого программными средствами
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 88beba371a9dd8ea54dabe8f541b4a01773982cb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="44ecc-102">Как изменить FlowDirection содержимого программными средствами</span><span class="sxs-lookup"><span data-stu-id="44ecc-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="44ecc-103">В этом примере показано, как программно изменить <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойство <xref:System.Windows.Controls.FlowDocumentReader>.</span><span class="sxs-lookup"><span data-stu-id="44ecc-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44ecc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="44ecc-104">Example</span></span>  
 <span data-ttu-id="44ecc-105">Два <xref:System.Windows.Controls.Button> создаются элементы, каждый из которых представляет одно из возможных значений <xref:System.Windows.FlowDirection>.</span><span class="sxs-lookup"><span data-stu-id="44ecc-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="44ecc-106">При нажатии кнопки значение связанного свойства применяется к содержимому <xref:System.Windows.Controls.FlowDocumentReader> с именем `tf1`.</span><span class="sxs-lookup"><span data-stu-id="44ecc-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="44ecc-107">Значение свойства также записывается <xref:System.Windows.Controls.TextBlock> с именем `txt1`.</span><span class="sxs-lookup"><span data-stu-id="44ecc-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="44ecc-108">Пример</span><span class="sxs-lookup"><span data-stu-id="44ecc-108">Example</span></span>  
 <span data-ttu-id="44ecc-109">События, связанные с нажатием кнопки, определенные выше, обрабатываются в файле кода C#.</span><span class="sxs-lookup"><span data-stu-id="44ecc-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
