---
title: "Практическое руководство. Замораживание столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], фиксация"
  - "DataGridView - элемент управления [Windows Forms], постоянно видимые столбцы"
  - "DataGridView - элемент управления [Windows Forms], фиксация столбцов"
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Замораживание столбцов элемента управления DataGridView в Windows Forms
При просмотре пользователями данных, отображаемых в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, им порой требуется часто обращаться к одному столбцу или набору столбцов.  Например, при просмотре таблицы сведений о пользователе, содержащей много столбцов, может быть желательно, чтобы имя пользователя отображалось постоянно при прокручивании остальных столбцов за пределы видимости.  
  
 Для этого необходимо закрепить столбцы в элементе управления.  При закреплении столбца все столбцы слева от него \(или справа для языков с направлением письма справа налево\) также закрепляются.  Закрепленные столбцы остаются на месте в то время, как остальные столбцы можно прокручивать.  
  
> [!NOTE]
>  Если разрешено переупорядочивание столбцов, закрепленные столбцы рассматриваются как группа, отличная от группы незакрепленных столбцов.  Пользователи могут переставлять местами столбцы в каждой из групп, но не могут перемещать столбцы из одной группы в другую.  
  
 Свойство <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> столбца определяет, должен ли он отображаться в сетке постоянно.  
  
 Эта задача поддерживается в Visual Studio.  См. также [Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).  
  
### Программное закрепление столбца  
  
-   Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `AddToCartButton`;  
  
-   ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)