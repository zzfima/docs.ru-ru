---
title: "Практическое руководство. Реализация декоративного элемента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "декоративные элементы, реализация"
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Реализация декоративного элемента
В этом примере показана минимальная реализация декоративного элемента.  
  
## Примечания по реализации  
 Важно обратить внимание, что декораторы не включают любое обязательное поведение отрисовки; гарантируется, что ответственность за отрисовку декоратора лежит на реализаторе декоратора.  Наиболее распространенный способ реализации поведения отрисовки состоит в переопределении метода <xref:System.Windows.UIElement.OnRender%2A> и использовании одного или нескольких объектов <xref:System.Windows.Media.DrawingContext> для отрисовки графических компонентов декоративного элемента по мере необходимости \(как показано в приведенном примере\).  
  
## Пример  
  
### Описание  
 Пользовательский декоратор создается путем реализации класса, который наследуется от абстрактного класса <xref:System.Windows.Documents.Adorner>.  В примере декоративный элемент просто украшает углы <xref:System.Windows.UIElement> кругами путем переопределения метода <xref:System.Windows.UIElement.OnRender%2A>.  
  
### Код  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)