---
title: "Практическое руководство. Реализация уведомления об изменении свойства | Microsoft Docs"
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
  - "уведомления об изменениях"
  - "привязка данных, уведомления об изменении свойств"
  - "уведомления об изменениях"
  - "свойства, уведомления об изменениях"
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Реализация уведомления об изменении свойства
Для поддержки привязок <xref:System.Windows.Data.BindingMode> или <xref:System.Windows.Data.BindingMode>, чтобы позволить вашим свойствам [источника привязки](GTMT) автоматически отражать динамические изменения [источника привязки](GTMT) \(например, провести предварительный просмотр области, автоматически обновляемой, когда пользователь редактирует форму\), классу необходимо предоставить соответствующие уведомления об изменении свойств.  В этом примере демонстрируется создание класса, который реализует <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## Пример  
 Для реализации <xref:System.ComponentModel.INotifyPropertyChanged> необходимо объявить событие <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> и создать метод `OnPropertyChanged`.  Затем для каждого свойства вам потребуются уведомления об изменениях, поэтому вы вызываете `OnPropertyChanged` при каждом обновлении свойства.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Пример того, как класс `Person` может использоваться для поддержки привязки <xref:System.Windows.Data.BindingMode>, см. в разделе [Управление обновлением источника из поля TextBox](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## См. также  
 [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)