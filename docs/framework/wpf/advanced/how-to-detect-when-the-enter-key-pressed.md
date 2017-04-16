---
title: "Практическое руководство. Определение нажатия клавиши &quot;Enter&quot; | Microsoft Docs"
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
  - "ВВОД - клавиша, обнаружение"
  - "ключи, ВВОД"
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Определение нажатия клавиши &quot;Enter&quot;
В этом примере показано, как определить, когда на клавиатуре нажата клавиша <xref:System.Windows.Input.Key>.  
  
 Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.  
  
## Пример  
 Когда пользователь нажимает клавишу <xref:System.Windows.Input.Key> в элементе управления <xref:System.Windows.Controls.TextBox>, входные данные текстового поля появляются в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 В следующем примере [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создается пользовательский интерфейс, состоящий из элементов <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 В следующем примере кода программной части создается обработчик событий <xref:System.Windows.UIElement.KeyDown>.  Если нажата клавиша <xref:System.Windows.Input.Key>, в элементе <xref:System.Windows.Controls.TextBlock> отображается сообщение.  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## См. также  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)