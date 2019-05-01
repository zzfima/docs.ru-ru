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
ms.openlocfilehash: 3263810806b6b4bbec15eadfd1f1da3a57d12698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052369"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>Практическое руководство. Установка полей для элементов и элементов управления
В этом примере описывается установка <xref:System.Windows.FrameworkElement.Margin%2A> свойства, путем изменения значения любого существующего свойства для поля в коде. <xref:System.Windows.FrameworkElement.Margin%2A> Свойство является свойством <xref:System.Windows.FrameworkElement> элемент базового и таким образом будет наследоваться различные элементы управления и другие элементы.  
  
 В этом примере создается на языке [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], файл с выделенным кодом, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ссылается на. Код программной части показан как C# и версии Microsoft Visual Basic.  
  
## <a name="example"></a>Пример  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
