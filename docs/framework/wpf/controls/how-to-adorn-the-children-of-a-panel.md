---
title: "Практическое руководство. Оформление дочерних объектов панели | Microsoft Docs"
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
  - "декоративные элементы, привязка к дочерним элементам Panel"
  - "Panel - элемент управления, привязка декоративных элементов к дочерним элементам"
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Оформление дочерних объектов панели
В этом примере демонстрируется привязка элемента оформления к дочерним элементам указанного <xref:System.Windows.Controls.Panel> программными средствами.  
  
## Пример  
 Для привязки элемента оформления к дочерним объектам <xref:System.Windows.Controls.Panel>, выполните следующие действия.  
  
1.  Объявите новый объект <xref:System.Windows.Documents.AdornerLayer> и вызовите метод `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>, чтобы установить уровень графического элемента для элемента, дочерние элементы которого надо оформить.  
  
2.  Выполните перечисление через дочерние элементы родительского элемента и вызовите метод <xref:System.Windows.Documents.AdornerLayer.Add%2A> для привязки элемента оформления к каждому дочернему элементу.  
  
 Следующий пример привязывает SimpleCircleAdorner \(показанный выше\) к дочерним элементам <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки элемента оформления к другому элементу в текущей версии не поддерживается.  
  
## См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)