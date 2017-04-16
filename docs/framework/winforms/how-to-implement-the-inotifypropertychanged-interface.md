---
title: "Практическое руководство. Реализация интерфейса INotifyPropertyChanged | Microsoft Docs"
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
  - "INotifyPropertyChanged - интерфейс, реализация"
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Реализация интерфейса INotifyPropertyChanged
В следующем примере показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>.  Реализуйте этот интерфейс в бизнес\-объекте, используемом в привязке данных Windows Forms.  После реализации этот интерфейс будет сообщать связанному элементу управления об изменениях свойств бизнес\-объекта.  
  
## Пример  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## См. также  
 [Практическое руководство. Применение шаблона PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Практическое руководство. Получение уведомления об изменении данных с использованием компонента BindingSource и интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)   
 [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)