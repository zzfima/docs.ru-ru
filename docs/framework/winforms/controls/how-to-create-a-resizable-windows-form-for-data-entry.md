---
title: "Практическое руководство. Создание в Windows Forms формы для ввода данных, размер которой можно изменять | Microsoft Docs"
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
  - "формы, создание переменного размера"
  - "макет [Windows Forms], изменение размеров"
  - "TableLayoutPanel - элемент управления [Windows Forms]"
  - "Windows Forms, изменяемого размера"
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Создание в Windows Forms формы для ввода данных, размер которой можно изменять
Удачно сконструированный макет должен реагировать на изменение размеров родительской формы.  Для согласованного изменения размера и положения элементов управления на макете формы при изменении размеров формы можно использовать элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.  Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> также полезен в случаях, когда изменение содержимого элементов управления приводит к изменению макета.  Процесс, описанный в этой процедуре, можно выполнить в среде Visual Studio.  См. также [Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](http://msdn.microsoft.com/library/991eahec\(v=vs.110\)).  
  
## Пример  
 В следующем примере демонстрируется использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для построения макета, который соответствующим образом меняется при изменении пользователем размера формы.  Он также демонстрирует, как макет учитывает будущую локализацию.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)   
 [Официальные рекомендации для разработчиков и проектировщиков интерфейса пользователя Microsoft Windows. Redmond, WA: Microsoft Press, 1999 г. \(USBN: 0\-7356\-0566\-1\)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)