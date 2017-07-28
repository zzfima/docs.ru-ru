---
title: "Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки | Microsoft Docs"
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
  - "привязка данных, получение объектов привязки из свойств целевого объекта привязки"
  - "свойства, получение объектов привязки"
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки
В этом примере показано, как получить объект привязки из свойства целевого объекта с привязкой данных.  
  
## Пример  
 Для получения объекта <xref:System.Windows.Data.Binding> можно сделать следующее:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  Необходимо указать [свойство зависимостей](GTMT) для нужной привязки, поскольку возможно, что привязка данных используется в нескольких свойствах целевого объекта.  
  
 Кроме того, можно получить <xref:System.Windows.Data.BindingExpression>, а затем получить значение свойства <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.  
  
 Полный код примера см. на веб\-странице [Пример Binding Validation](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Если привязка представляет собой <xref:System.Windows.Data.MultiBinding>, используйте <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.  Если она представляет собой <xref:System.Windows.Data.PriorityBinding>, используйте <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.  Если вы не уверены, привязано ли свойство целевого объекта с использованием <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding> или <xref:System.Windows.Data.PriorityBinding>, можно использовать <xref:System.Windows.Data.BindingOperations>. <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## См. также  
 [Создание привязки в коде](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)