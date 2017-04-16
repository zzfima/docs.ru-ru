---
title: "Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
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
  - "DataGridView - элемент управления [Windows Forms], форм с отношением "главный-подчиненный""
  - "списки типа "основной-подробности", создание"
  - "таблицы с отношением подчинения, отображение в формах Windows Forms"
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms
В приведенном ниже примере кода создаются главная и подчиненная формы с использованием двух элементов управления <xref:System.Windows.Forms.DataGridView>, привязанных к двум компонентам <xref:System.Windows.Forms.BindingSource>.  Источником данных является объект <xref:System.Data.DataSet>, содержащий таблицы `Customers` и `Orders` из образца базы данных SQL Server Northwind и объект <xref:System.Data.DataRelation>, связывающий таблицы через столбец `CustomerID`.  
  
 Один источник <xref:System.Windows.Forms.BindingSource> привязан к родительской таблице `Customers` в наборе данных.  Эти данные отображаются в главном элементе управления <xref:System.Windows.Forms.DataGridView>.  Другой источник <xref:System.Windows.Forms.BindingSource> привязан к первому соединителю данных.  Свойству <xref:System.Windows.Forms.BindingSource.DataMember%2A> второго источника <xref:System.Windows.Forms.BindingSource> присвоено имя <xref:System.Data.DataRelation>.  Это заставляет связанный подчиненный элемент управления <xref:System.Windows.Forms.DataGridView> отображать строки дочерней таблицы `Orders`, соответствующие текущей строке главного элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 Полное описание этого примера кода см. в разделе [Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagrids.md).  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Windows.Forms и System.XML.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Безопасность платформы .NET Framework  
 Хранение конфиденциальных сведений \(например, пароля\) в строке подключения может повлиять на безопасность приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Подробнее см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagrids.md)   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)