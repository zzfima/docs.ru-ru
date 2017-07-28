---
title: "Практическое руководство. Применение шаблона PropertyNameChanged | Microsoft Docs"
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
  - "пользовательские элементы управления [Windows Forms], изменение свойств (с использованием кода)"
  - "привязка данных, пользовательские элементы управления"
  - "PropertyNameChanged шаблон, применение"
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Применение шаблона PropertyNameChanged
В представленном ниже примере кода демонстрируется применение шаблона *PropertyName*Changed к пользовательскому элементу управления.  Применяйте этот шаблон при реализации пользовательских элементов управления, используемых вместе с ядром привязки данных Windows Forms.  
  
## Пример  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## Компиляция кода  
 Компиляция предыдущего примера кода  
  
-   Вставьте код в пустой файл кода.  Пользовательский элемент управления необходимо использовать в форме Windows Form, содержащей метод `Main`.  
  
## См. также  
 [Практическое руководство. Реализация интерфейса INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)   
 [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)