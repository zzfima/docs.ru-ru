---
title: Поиск элемента, созданного шаблоном ControlTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 232ee7d2859059591c9beff753f45781598a8127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460707"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Поиск элемента, созданного шаблоном ControlTemplate
В этом примере показано, как найти элементы, создаваемые <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Пример  
 В следующем примере показан стиль, создающий простой <xref:System.Windows.Controls.ControlTemplate> для класса <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Чтобы найти элемент в шаблоне после применения шаблона, можно вызвать метод <xref:System.Windows.FrameworkTemplate.FindName%2A> <xref:System.Windows.Controls.Control.Template%2A>. В следующем примере создается окно сообщения, в котором отображается фактическое значение ширины <xref:System.Windows.Controls.Grid> в шаблоне элемента управления:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>См. также

- [Поиск элементов, созданных с использованием шаблона DataTemplate](../data/how-to-find-datatemplate-generated-elements.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Области видимости имен XAML в WPF](../advanced/wpf-xaml-namescopes.md)
- [Деревья в WPF](../advanced/trees-in-wpf.md)
