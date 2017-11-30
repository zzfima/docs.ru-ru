---
title: "Поиск элемента, созданного шаблоном ControlTemplate"
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
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f81069873930af57e1f6ab2f3e0408b4d53f38b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Поиск элемента, созданного шаблоном ControlTemplate
В этом примере показано, как найти элементы, созданные <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано стиль, который создает простой <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> класса:  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Чтобы найти элемент в шаблоне, после применения шаблона, можно вызвать <xref:System.Windows.FrameworkTemplate.FindName%2A> метод <xref:System.Windows.Controls.Control.Template%2A>. В следующем примере создается окно сообщения, которое показывает фактическое значение ширины <xref:System.Windows.Controls.Grid> в шаблоне элемента управления:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>См. также  
 [Поиск элементов, созданных с использованием шаблона DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
