---
title: "Как изменить типа курсора | Microsoft Docs"
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
  - "WPF"
  - "курсор (указатель мыши), тип курсора"
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Как изменить типа курсора
В этом примере демонстрируется изменение объекта <xref:System.Windows.Input.Cursor> указателя мыши для отдельного элемента и приложения.  
  
 Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла с выделенным кодом.  
  
## Пример  
 Создаваемый пользовательский интерфейс состоит из объекта <xref:System.Windows.Controls.ComboBox> для выбора нужного объекта <xref:System.Windows.Input.Cursor>, пары объектов <xref:System.Windows.Controls.RadioButton>, чтобы определить изменение курсора для одного элемента или для всего приложения, и объекта <xref:System.Windows.Controls.Border>, который является элементом, к которому применяется новый курсор.  
  
 [!code-xml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Следующий фоновый код создает обработчик событий <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>, который вызывается, когда тип курсора изменяется в объекте <xref:System.Windows.Controls.ComboBox>.  Инструкция переключателя фильтрует имя курсора и задает свойство <xref:System.Windows.FrameworkElement.Cursor%2A> в объекте <xref:System.Windows.Controls.Border> с именем *DisplayArea*.  
  
 Если изменение курсора установлено для «Всего приложения», свойство <xref:System.Windows.Input.Mouse.OverrideCursor%2A> устанавливается в свойство <xref:System.Windows.FrameworkElement.Cursor%2A> элемента управления <xref:System.Windows.Controls.Border>.  Это заставляет курсор изменяться для всего приложения.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## См. также  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)