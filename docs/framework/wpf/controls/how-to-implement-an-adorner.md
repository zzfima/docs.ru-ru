---
title: "Практическое руководство. Реализация декоративного элемента"
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f69fee64ea65e8d49cce523c85669993cc6bce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-implement-an-adorner"></a>Практическое руководство. Реализация декоративного элемента
В этом примере показана реализация минимальной графических элементов.  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Важно отметить, что декоративные элементы не включают какое-либо обязательное поведение отрисовки. За результат применения декоративного элемента отвечает его автор.   Распространенным способом реализации поведения визуализации является переопределение <xref:System.Windows.UIElement.OnRender%2A> метод и использование одного или нескольких <xref:System.Windows.Media.DrawingContext> объектов для подготовки к просмотру декоратора по мере необходимости (как показано в следующем примере).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Пользовательский графический элемент создается путем реализации класса, который наследует от абстрактного <xref:System.Windows.Documents.Adorner> класса.  В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> кругами путем переопределения <xref:System.Windows.UIElement.OnRender%2A> метод.  
  
### <a name="code"></a>Код  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)
