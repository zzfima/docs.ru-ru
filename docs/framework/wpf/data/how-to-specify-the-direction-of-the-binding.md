---
title: "Практическое руководство. Указание направления привязки | Microsoft Docs"
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
  - "направление привязки"
  - "привязка данных, направление привязки"
  - "направление привязки"
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Практическое руководство. Указание направления привязки
Этот пример показывает, как указать, что привязка обновляет только свойство [цели привязки](GTMT) \(цель\), свойство [источника привязки](GTMT) \(источник\), или обновляет свойство цели и свойство источника.  
  
## Пример  
 Вы используете свойство <xref:System.Windows.Data.Binding.Mode%2A> для указания направления привязки.  В следующем списке перечислены доступные параметры для обновлений привязки:  
  
-   <xref:System.Windows.Data.BindingMode> обновляет свойство цели или свойство источника при изменении свойства цели или свойства источника.  
  
-   <xref:System.Windows.Data.BindingMode> обновляет только свойство цели при изменении свойства источника.  
  
-   <xref:System.Windows.Data.BindingMode> обновляет только свойство цели при запуске приложения, или когда <xref:System.Windows.FrameworkElement.DataContext%2A> подвергается изменению.  
  
-   <xref:System.Windows.Data.BindingMode> обновляет только свойство источника при изменении свойства цели.  
  
-   <xref:System.Windows.Data.BindingMode> вызывает значение <xref:System.Windows.Data.Binding.Mode%2A> по умолчанию используемого свойства цели.  
  
 Дополнительные сведения см. в разделе <xref:System.Windows.Data.BindingMode>.  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Для обнаружения изменений в источнике \(применимо для типов связывания <xref:System.Windows.Data.BindingMode> и <xref:System.Windows.Data.BindingMode>\), источник должен реализовывать подходящий механизм уведомления об изменении свойства, такой как <xref:System.ComponentModel.INotifyPropertyChanged>.  Пример реализации класса <xref:System.ComponentModel.INotifyPropertyChanged> см. в разделе [Реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Для привязок <xref:System.Windows.Data.BindingMode> или <xref:System.Windows.Data.BindingMode>, вы можете управлять временем обновлений источника путем задания свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## См. также  
 <xref:System.Windows.Data.Binding>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)