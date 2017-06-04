---
title: "Практическое руководство. Закрепление элементов управления в формах Windows Forms. | Microsoft Docs"
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
  - "элементы управления [Windows Forms], закрепление"
  - "Dock - свойство"
  - "приложения в стиле обозревателя, создание"
  - "элементы управления Windows Forms, заполнение клиентской области"
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Закрепление элементов управления в формах Windows Forms.
Можно закрепить элементы управления на границах формы или заполнить ими контейнер элемента управления \(форму или контейнерный элемент управления\).  Например, проводник Windows закрепляет элемент управления <xref:System.Windows.Forms.TreeView> у левой стороны окна, а элемент управления <xref:System.Windows.Forms.ListView> – у правой стороны.  Свойство <xref:System.Windows.Forms.Control.Dock%2A> используется для всех видимых элементов управления Windows Forms для определения режима закрепления.  
  
> [!NOTE]
>  Элементы закрепляются в обратном z\-порядке.  
  
 Свойство <xref:System.Windows.Forms.Control.Dock%2A> взаимодействует со свойством <xref:System.Windows.Forms.Control.AutoSize%2A>.  Дополнительные сведения см. в разделе [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### Чтобы закрепить элемент управления  
  
1.  Выберите элемент управления, который следует закрепить.  
  
2.  В окне "Свойства" щелкните стрелку справа от свойства <xref:System.Windows.Forms.Control.Dock%2A>.  
  
     Отображается редактор, показывающий набор полей, соответствующих краям и центру формы.  
  
3.  Нажмите кнопку, соответствующую краю формы, где следует закрепить элемент управления.  Чтобы заполнить содержимое формы элемента управления или контейнерного элемента управления, щелкните центральное поле.  Щелкните **\(нет\)** для запрещения закрепления.  
  
     Элемент управления автоматически изменяет свой размер, чтобы соответствовать границам закрепленного края.  
  
    > [!NOTE]
    >  Унаследованные элементы управления можно закреплять, только если они являются `Protected`.  Чтобы изменить уровень доступа к элементу управления, задайте его свойство **Модификатор** в окне "Свойства".  
  
## См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Расположение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Практическое руководство. Привязка элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)