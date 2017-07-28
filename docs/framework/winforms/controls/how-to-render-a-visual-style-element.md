---
title: "Практическое руководство. Отображение элементов с использованием визуальных стилей | Microsoft Docs"
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
  - "профессиональный вид, применение к элементам приложений Windows Forms"
  - "визуальные стили, отрисовка элементов управления Windows Forms"
  - "визуальные темы, применение к элементам приложений Windows Forms"
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Отображение элементов с использованием визуальных стилей
Пространство имен <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> обеспечивает объекты <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, представляющие элементы пользовательского интерфейса Windows с поддержкой визуальных стилей.  В этом разделе показано, как использовать класс <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> для визуализации элемента <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, представляющего кнопки **Выход** и **Выключение** в меню "Пуск".  
  
### Прорисовка элемента визуального стиля  
  
1.  Создайте <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> и присвойте ему элемент, которые требуется нарисовать.  Обратите внимание на использование свойства <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=fullName> и метода <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=fullName>; конструктор <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> выдаст исключение, если визуальные стили отключены или элемент не определен.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Вызовите метод <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> для визуализации элемента, который <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> в данный момент представляет.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Пользовательский элемент управления, производный от класса <xref:System.Windows.Forms.Control>.  
  
-   <xref:System.Windows.Forms.Form> с элементом управления.  
  
-   Ссылки на пространства имен <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> и <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>.  
  
## См. также  
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)