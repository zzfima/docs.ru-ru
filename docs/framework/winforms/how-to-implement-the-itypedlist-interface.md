---
title: "Практическое руководство. Реализация интерфейса ITypedList | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingList(Of T) - класс"
  - "привязка данных, реализация"
  - "IBindingList - интерфейс"
  - "ITypedList - интерфейс"
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Реализация интерфейса ITypedList
Реализуйте интерфейс <xref:System.ComponentModel.ITypedList>, чтобы включить обнаружение схемы для связываемого списка.  
  
## Пример  
 В следующем примере показано, как реализовать интерфейс <xref:System.ComponentModel.ITypedList>.  Общий тип с именем `SortableBindingList` является производным от класса <xref:System.ComponentModel.BindingList%601>. Этот тип реализует интерфейс <xref:System.ComponentModel.ITypedList>.  Простой класс с именем `Customer` предоставляет данные, которые привязаны к заголовку элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на сборки System.Drawing и System.Windows.Forms.  
  
## См. также  
 <xref:System.ComponentModel.ITypedList>   
 <xref:System.ComponentModel.BindingList%601>   
 <xref:System.ComponentModel.IBindingList>   
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)