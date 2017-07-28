---
title: "Практическое руководство. Реализация проверки для пользовательских объектов | Microsoft Docs"
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
  - "поиск ошибок проверки [WPF]"
  - "пользовательские объекты [WPF], реализация проверки"
  - "реализация проверки для пользовательских объектов [WPF]"
  - "ошибки проверки [WPF], поиск"
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Реализация проверки для пользовательских объектов
В этом примере демонстрируется реализация проверки для пользовательского объекта и последующей привязки к нему.  
  
## Пример  
 Можно обеспечить проверку для бизнес\-слоя, если источник объекта реализует <xref:System.ComponentModel.IDataErrorInfo>, как показано в следующем примере:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 В следующем примере свойство Text текстового поля привязывается к свойству `Age` объекта `Person`, который был сделан доступным для привязки через объявление ресурса, предоставляемое `x:Key` `data`.  <xref:System.Windows.Controls.DataErrorValidationRule> следит за ошибками проверки, вызываемыми реализацией <xref:System.ComponentModel.IDataErrorInfo>.  
  
 [!code-xml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 Кроме того, вместо использования <xref:System.Windows.Controls.DataErrorValidationRule> можно задать для свойства <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> значение `true`.  
  
## См. также  
 <xref:System.Windows.Controls.ExceptionValidationRule>   
 [Реализация проверки привязки](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)