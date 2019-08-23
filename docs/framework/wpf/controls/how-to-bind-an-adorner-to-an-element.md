---
title: Практическое руководство. Привязка декоративного элемента к элементу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: e8c7eb929042bfe1455bfc9bf459fc466de5c397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923495"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Практическое руководство. Привязка декоративного элемента к элементу
В этом примере показано, как программно привязать декоративный элемент <xref:System.Windows.UIElement>к указанному.  
  
## <a name="example"></a>Пример  
 Чтобы привязать декоративный элемент к конкретному <xref:System.Windows.UIElement>, выполните следующие действия.  
  
1. Вызовите <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> <xref:System.Windows.Documents.AdornerLayer> метод, чтобы получить объект для элемента <xref:System.Windows.UIElement> , который должен быть оформлен. `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>переходит вверх по визуальному дереву, начиная с указанного **UIElement**, и возвращает первый найденный слой декоративных элементов. (Если слои декоративных элементов не найдены, метод возвращает значение 0.)  
  
2. Вызовите метод, чтобы привязать декоративный элемент к целевому объекту **UIElement.** <xref:System.Windows.Documents.AdornerLayer.Add%2A>  
  
 В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше <xref:System.Windows.Controls.TextBox> ) к именованной *митекстбокс*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о декоративных элементах](adorners-overview.md)
