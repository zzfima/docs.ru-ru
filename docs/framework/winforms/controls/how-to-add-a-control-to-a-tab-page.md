---
title: "Практическое руководство. Добавление элемента управления на вкладку | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления вкладка, последовательность вкладок"
  - "страницы вкладок, добавление элементов управления"
  - "TabPage - элемент управления"
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Добавление элемента управления на вкладку
Элемент управления <xref:System.Windows.Forms.TabControl> конструктора Windows Forms можно использовать для упорядочения отображения других элементов управления.  Ниже показано, как добавить кнопку в первую вкладку.  Дополнительные сведения о добавлении значка в область надписей на вкладке см. в разделе [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### Чтобы добавить элемент управления программными средствами, выполните следующие действия:  
  
1.  Используйте метод <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> коллекции, возвращаемой свойством <xref:System.Windows.Forms.Control.Controls%2A> элемента управления <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## См. также  
 [Элемент управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)   
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)