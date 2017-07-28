---
title: "Практическое руководство. Настройка уведомлений обновлений привязок | Microsoft Docs"
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
  - "привязка, обновления, уведомления о"
  - "привязка данных, уведомление об обновлениях привязки"
  - "уведомления, обновления привязки"
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Настройка уведомлений обновлений привязок
В этом примере демонстрируется настройка уведомления, когда свойство [целевого объекта привязки](GTMT) \(цели\) или [исходного объекта привязки](GTMT) \(источника\) было обновлено.  
  
## Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] вызывает событие обновления данных каждый раз при обновлении источника или цели привязки.  Внутри это событие используется для информирования [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что он должен быть обновлен, поскольку связанные данные были изменены.  Обратите внимание, что для работы этих событий, а также для правильной работы односторонней или двусторонней привязки необходимо реализовать класс данных с помощью интерфейса <xref:System.ComponentModel.INotifyPropertyChanged>.  Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Установите свойство <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> или <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> \(или оба\) в значение `true` в привязке.  Обработчик, который предоставляется для прослушивания данного события, должен быть присоединен непосредственно к элементу, об изменениях которого необходимо информировать, или к контексту общих данных, если необходимо информировать обо всех изменениях в контексте.  
  
 Здесь приведен пример, который показывает, как установить уведомление при обновлении нужного свойства.  
  
 [!code-xml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Затем для обработки события можно назначить обработчик, основанный на делегате EventHandler\<T\>, в данном примере на *OnTargetUpdated*:  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Параметры события можно использовать для задания сведений о свойстве, которое было изменено \(например тип или конкретный элемент, если один и тот же обработчик подключен к нескольким элементам\), что может быть полезно, если имеются несколько связанных свойств для одного элемента.  
  
## См. также  
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)