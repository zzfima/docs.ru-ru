---
title: Практическое руководство. Установка полей для элементов и элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 41a0f1d025061cc7c1472a831fbbd5ed2f01b043
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="b65c0-102">Практическое руководство. Установка полей для элементов и элементов управления</span><span class="sxs-lookup"><span data-stu-id="b65c0-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="b65c0-103">В этом примере описывается, как задать <xref:System.Windows.FrameworkElement.Margin%2A> свойства путем изменения значения любого существующего свойства для поля в коде.</span><span class="sxs-lookup"><span data-stu-id="b65c0-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="b65c0-104"><xref:System.Windows.FrameworkElement.Margin%2A> Свойство является свойством <xref:System.Windows.FrameworkElement> элемент базового и поэтому оно наследуется различных элементов управления и других элементов.</span><span class="sxs-lookup"><span data-stu-id="b65c0-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="b65c0-105">В этом примере записывается [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], файл с выделенным кодом, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ссылается.</span><span class="sxs-lookup"><span data-stu-id="b65c0-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="b65c0-106">Код программной части отображается в C# и версии Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b65c0-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b65c0-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b65c0-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
