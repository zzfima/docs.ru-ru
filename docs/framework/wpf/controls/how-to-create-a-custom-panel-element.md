---
title: "Практическое руководство. Создание пользовательского элемента Panel"
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
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e7cca5b6f7a0d5085e70c4ab6ac33ff83b75217
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="cdaaf-102">Практическое руководство. Создание пользовательского элемента Panel</span><span class="sxs-lookup"><span data-stu-id="cdaaf-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="cdaaf-103">Пример</span><span class="sxs-lookup"><span data-stu-id="cdaaf-103">Example</span></span>  
 <span data-ttu-id="cdaaf-104">В этом примере показан способ переопределения поведения по умолчанию <xref:System.Windows.Controls.Panel> элемент и создание пользовательских элементов макета, производных от <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="cdaaf-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="cdaaf-105">В примере определяется простой пользовательский <xref:System.Windows.Controls.Panel> элемент с именем `PlotPanel`, который размещает дочерние элементы в соответствии с двумя жестко координаты x и y-.</span><span class="sxs-lookup"><span data-stu-id="cdaaf-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="cdaaf-106">В этом примере `x` и `y` устанавливаются равными `50`; таким образом, все дочерние элементы располагаются в этом расположении на x и y осей.</span><span class="sxs-lookup"><span data-stu-id="cdaaf-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="cdaaf-107">Чтобы реализовать пользовательскую <xref:System.Windows.Controls.Panel> поведения, в примере используется <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="cdaaf-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="cdaaf-108">Каждый метод возвращает <xref:System.Windows.Size> данные, необходимые для размещения и отображения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="cdaaf-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cdaaf-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cdaaf-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="cdaaf-110">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="cdaaf-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="cdaaf-111">Создать пользовательский образец панели с переносом содержимого</span><span class="sxs-lookup"><span data-stu-id="cdaaf-111">Create a Custom Content-Wrapping Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159979)
