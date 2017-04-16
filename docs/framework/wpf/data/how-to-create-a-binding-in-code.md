---
title: "Практическое руководство. Создание привязки в коде | Microsoft Docs"
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
  - "привязка данных, создание"
  - "привязка данных, создание"
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Практическое руководство. Создание привязки в коде
В этом примере демонстрируется создание и установка <xref:System.Windows.Data.Binding> в коде.  
  
## Пример  
 Классы <xref:System.Windows.FrameworkElement> и <xref:System.Windows.FrameworkContentElement> предоставляют метод `SetBinding`.  В случае привязки элемента, наследующего от любого из этих классов, можно напрямую вызвать метод <xref:System.Windows.FrameworkElement.SetBinding%2A>.  
  
 В следующем примере создается класс с именем `MyData`, содержащий свойство с именем `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 В примере показано создание объекта привязки для задания источника привязки.  В примере используется метод <xref:System.Windows.FrameworkElement.SetBinding%2A> для привязки свойства <xref:System.Windows.Controls.TextBlock.Text%2A> объекта `myText`, который является элементом управления <xref:System.Windows.Controls.TextBlock>, к объекту `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Полный пример кода см. в разделе [Code\-only Binding Sample](http://msdn.microsoft.com/ru-ru/764aaf0b-2216-4941-9548-9c98da18d1a6).  
  
 Вместо вызова метода <xref:System.Windows.FrameworkElement.SetBinding%2A>, можно использовать статический метод <xref:System.Windows.Data.BindingOperations.SetBinding%2A> класса <xref:System.Windows.Data.BindingOperations>.  В следующем примере для привязки элемента управления `myText` к объекту `myDataProperty` вместо метода <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=fullName> вызывается метод <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName>.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)