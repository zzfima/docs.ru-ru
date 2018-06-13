---
title: Практическое руководство. Привязка графического элемента к элементу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: fb419ee5a57e81e7e3bc72ae04fd200703b80cd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552556"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Практическое руководство. Привязка графического элемента к элементу
В этом примере показано, как программным способом привязки графического элемента с заданным <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Пример  
 Для привязки к конкретному графический элемент <xref:System.Windows.UIElement>, выполните следующие действия:  
  
1.  Вызовите `static` метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> для получения <xref:System.Windows.Documents.AdornerLayer> для объекта <xref:System.Windows.UIElement> оформляемого. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> перемещается вверх по дереву visual, начиная с указанного **UIElement**и возвращает первый слой графических элементов, которые найдет. (Если слои декоративных элементов не найдены, метод возвращает значение 0.)  
  
2.  Вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки к целевому декоратора **UIElement**.  
  
 Следующий пример привязывает (показано выше) для SimpleCircleAdorner <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)
