---
title: "Слияние элементов меню в элементе управления MenuStrip в Windows Forms | Microsoft Docs"
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
  - "MenuStrip, слияние"
  - "слияние, общие понятия"
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Слияние элементов меню в элементе управления MenuStrip в Windows Forms
В приложении интерфейса MDI можно объединять пункты меню или целые меню из родительского окна MDI.  
  
 В этом разделе описаны основные понятия, относящиеся к слиянию пунктов меню в приложении интерфейса MDI.  
  
## Общие понятия  
 Процедуры слияния охватывают как целевой, так и исходный элемент управления.  
  
-   Целевым является элемент управления <xref:System.Windows.Forms.MenuStrip> на главной или родительской форме MDI, с которой выполняется слияние пунктов меню.  
  
-   Исходным является элемент управления <xref:System.Windows.Forms.MenuStrip> на дочерней форме MDI, содержащей пункты меню, которые требуется объединить с целевым меню.  
  
 Свойство <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> определяет пункт меню, раскрывающийся список которого будет заполнен заголовками дочерних форм MDI текущей родительской формы MDI.  Например, в список обычно включаются дочерние формы MDI, открытые в данный момент в меню **Окно**.  
  
 Свойство <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> определяет пункты меню, принимаемые от <xref:System.Windows.Forms.MenuStrip> на дочерней форме MDI.  
  
 Пункты меню можно объединить вручную или автоматически.  Слияние пунктов меню для обоих методов происходит одинаково, но включается по\-разному. Описание см. в подразделах "Слияние вручную" и "Автоматическое слияние" далее в этом разделе.  Как в слиянии вручную, так и при автоматическом слиянии, каждое действие слияния затрагивает следующее.  
  
 При слиянии <xref:System.Windows.Forms.MenuStrip> пункты меню перемещаются из одного <xref:System.Windows.Forms.ToolStrip> в другой, а не клонируются, как это происходит с <xref:System.Windows.Forms.MainMenu>.  
  
## Значения MergeAction  
 Для настройки операции слияния пунктов меню в исходной форме <xref:System.Windows.Forms.MenuStrip> служит свойство <xref:System.Windows.Forms.MergeAction>.  
  
 В следующей таблице описано значение и типичные случаи использования доступных операций слияния.  
  
|Значение MergeAction|Описание|Типичное использование|  
|--------------------------|--------------|----------------------------|  
|<xref:System.Windows.Forms.MergeAction>|\(По умолчанию\) Добавление исходного пункта в конец коллекции целевых пунктов.|Добавление пунктов меню в конец меню при активации определенной части программы.|  
|<xref:System.Windows.Forms.MergeAction>|Добавление исходного пункта в коллекцию целевых пунктов в положение, определенное свойством <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> исходного пункта.|Добавление пунктов меню в середину или начало меню при активации определенной части программы.<br /><br /> Если значение <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> одинаково для обоих пунктов меню, он добавляются в обратном порядке.  Для сохранения исходного порядка задайте соответствующее значение <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>.|  
|<xref:System.Windows.Forms.MergeAction>|Поиск текстового совпадения или использование значения <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>, если текстовое совпадение не найдено, и замена совпавшего целевого пункта меню исходным пунктом меню.|Замена целевого пункта меню исходным пунктом меню с тем же именем, действие которого отличается.|  
|<xref:System.Windows.Forms.MergeAction>|Поиск текстового совпадения или использование значения <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>, если текстовое совпадение не найдено, и добавление всех исходных пунктов раскрывающегося списка в целевые.|Построение структуры меню, в котором пункты включаются или добавляются в подменю или удаляются из него.  Например, пункт меню из дочерней формы MDI можно добавить в главное меню <xref:System.Windows.Forms.MenuStrip> **Сохранить как**.<br /><br /> <xref:System.Windows.Forms.MergeAction> позволяет переходить по структуре меню без выполнения каких\-либо действий.  Это позволяет оценить последующие пункты.|  
|<xref:System.Windows.Forms.MergeAction>|Поиск текстового совпадения или использование значения <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>, если текстовое совпадение не найдено, и удаление пункта из целевой формы.|Удаление пункта меню из целевой формы <xref:System.Windows.Forms.MenuStrip>.|  
  
## Слияние вручную  
 В автоматическом слиянии может принимать участие только элемент управления <xref:System.Windows.Forms.MenuStrip>.  Чтобы объединить пункты других элементов управления, таких как <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.StatusStrip>, слияние нужно выполнить вручную, вызвав методы <xref:System.Windows.Forms.ToolStripManager.Merge%2A> и <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> в коде в зависимости от необходимости.  
  
## Автоматическое слияние  
 Автоматическое слияние для приложений интерфейса MDI можно использовать путем активации исходной формы.  Чтобы использовать <xref:System.Windows.Forms.MenuStrip> в приложении интерфейса MDI, свойству <xref:System.Windows.Forms.Form.MainMenuStrip%2A> присвойте целевую форму <xref:System.Windows.Forms.MenuStrip>, так чтобы операции слияния, выполняемых с исходной формой <xref:System.Windows.Forms.MenuStrip>, отражались в целевой форме <xref:System.Windows.Forms.MenuStrip>.  
  
 Автоматическое слияние можно вызвать путем активации <xref:System.Windows.Forms.MenuStrip> на исходной форме MDI.  При активации исходная форма <xref:System.Windows.Forms.MenuStrip> сливается с целевой формой MDI.  После активации новой формы слияние отменяется на последней форме и вызывается в новой.  Этим поведением можно управлять, присвоив свойству <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> необходимое значение для каждого <xref:System.Windows.Forms.ToolStripItem>, и задав свойство <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> на каждом <xref:System.Windows.Forms.MenuStrip>.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)   
 [Практическое руководство. Автоматическое слияние меню в приложениях MDI](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)