---
title: "Практическое руководство. Растягивание ToolStripTextBox для заполнения оставшегося пространства элемента управления ToolStrip (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "текстовые поля, растяжение в элементе управления ToolStrip [Windows Forms]"
  - "ToolStrip - элемент управления [Windows Forms], растяжение текстового поля"
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Растягивание ToolStripTextBox для заполнения оставшегося пространства элемента управления ToolStrip (Windows Forms)
Если для свойства <xref:System.Windows.Forms.ToolStrip.Stretch%2A> элемента управления <xref:System.Windows.Forms.ToolStrip> задается значение `true`, элемент управления заполняет контейнер от начала до конца и изменяется в размерах при изменении размеров контейнера.  В такой конфигурации может оказаться полезным растяжение элемента в элементе управления, например <xref:System.Windows.Forms.ToolStripTextBox>, для заполнения доступного пространства и изменения размеров при изменении размеров элемента управления.  Возможность растяжения полезна, например, если требуется обеспечить внешний вид и поведение, аналогичные адресной строке Microsoft® Internet Explorer.  
  
## Пример  
 В следующем примере кода представлен класс, являющийся производным от <xref:System.Windows.Forms.ToolStripTextBox> с именем `ToolStripSpringTextBox`.  Этот класс переопределяет метод <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> для вычисления доступной ширины родительского элемента управления <xref:System.Windows.Forms.ToolStrip> после вычитания объединенной ширины остальных элементов.  В данном примере кода также представлен класс <xref:System.Windows.Forms.Form> и класс `Program`, демонстрирующие новое поведение.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripTextBox>   
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=fullName>   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)