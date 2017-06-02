---
title: "Практическое руководство. Создание объекта, следующего за указателем мыши | Microsoft Docs"
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
  - "WPF, следование объектов за"
  - "следование за указателем мыши (курсором)"
  - "курсор (указатель мыши), следование объектов за"
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Создание объекта, следующего за указателем мыши
В этом примере показан способ изменения размеров объекта при передвижении указателя мыши по экрану.  
  
 Пример включает файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], который создает [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] и файл кода программной части, который создает обработчик событий.  
  
## Пример  
 В следующем примере [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создается [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который состоит из фигуры <xref:System.Windows.Shapes.Ellipse> в элементе управления <xref:System.Windows.Controls.StackPanel>, и присоединяется обработчик событий для события <xref:System.Windows.UIElement.MouseMove>.  
  
 [!code-xml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Следующий код создает обработчик событий <xref:System.Windows.UIElement.MouseMove>.  Когда указатель мыши перемещается, высота и ширина <xref:System.Windows.Shapes.Ellipse> увеличивается и уменьшается.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## См. также  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)