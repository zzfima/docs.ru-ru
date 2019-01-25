---
title: Как выполнить Реализация декоративного элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: f34bdeb87d0bf34a998f9b2e2fb6c42aedec5063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591686"
---
# <a name="how-to-implement-an-adorner"></a>Как выполнить Реализация декоративного элемента
В этом примере показана реализация минимальной декоративного элемента.  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.   Распространенным способом реализации поведения отрисовки является переопределение <xref:System.Windows.UIElement.OnRender%2A> метод и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объекты для отрисовки декоративных элементов по мере необходимости (как показано в следующем примере).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 Пользовательский декоративный элемент создается путем реализации класс, наследующий от абстрактного <xref:System.Windows.Documents.Adorner> класса.  В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> кругами путем переопределения <xref:System.Windows.UIElement.OnRender%2A> метод.  
  
### <a name="code"></a>Код  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)
