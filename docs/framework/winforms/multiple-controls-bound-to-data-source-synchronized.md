---
title: "Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных | Microsoft Docs"
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
  - "элементы управления [Windows Forms], привязка нескольких объектов"
  - "элементы управления [Windows Forms], синхронизация с источником данных"
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных
Зачастую при работе с привязкой данных в Windows Forms несколько элементов управления привязываются к одному источнику данных.  Чтобы обеспечить синхронизацию элементов управления между собой и с источником данных, в некоторых случаях приходится выполнять некоторые дополнительные шаги.  Эти шаги необходимо выполнять в двух ситуациях, описанных ниже.  
  
-   Источник данных не реализует интерфейс <xref:System.ComponentModel.IBindingList>, и поэтому вызывает событие <xref:System.ComponentModel.IBindingList.ListChanged> типа <xref:System.ComponentModel.ListChangedType>.  
  
-   Если источник данных реализует интерфейс <xref:System.ComponentModel.IEditableObject>.  
  
 В первом из указанных выше случаев можно использовать компонент <xref:System.Windows.Forms.BindingSource> для привязки источника данных к элементам управления.  Во втором случае следует использовать компонент <xref:System.Windows.Forms.BindingSource>, обработать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> и вызвать метод <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> для связанного объекта <xref:System.Windows.Forms.BindingManagerBase>.  
  
## Пример  
 Ниже представлен пример кода, в котором показано, как привязать три элемента управления — два элемента управления текстового поля и один элемент <xref:System.Windows.Forms.DataGridView> — к одному столбцу в наборе <xref:System.Data.DataSet> с помощью компонента <xref:System.Windows.Forms.BindingSource>.  В следующем примере показано, как обработать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> и обеспечить обновление элемента управления <xref:System.Windows.Forms.DataGridView> и текстового поля правильным значением при изменении значения в другом текстовом поле.  
  
 В данном примере для привязки источника данных к элементам управления используется компонент <xref:System.Windows.Forms.BindingSource>.  Можно также непосредственно привязать элементы управления к источнику данных и извлечь объект <xref:System.Windows.Forms.BindingManagerBase> для привязки из объекта <xref:System.Windows.Forms.Control.BindingContext%2A> формы, после чего обработать событие <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> для объекта <xref:System.Windows.Forms.BindingManagerBase>.  Пример осуществления подобной процедуры см. на странице справки, посвященной событию <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> класса <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## Компиляция кода  
  
-   Для этого примера кода требуются перечисленные ниже компоненты.  
  
-   Ссылки на сборки <xref:System>, <xref:System.Windows.Forms>, и <xref:System.Drawing>.  
  
-   Форма с обработанным событием <xref:System.Windows.Forms.Form.Load> и вызовом метода `InitializeControlsAndDataSource` в примере из обработчика <xref:System.Windows.Forms.Form.Load> формы.  
  
## См. также  
 [Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)   
 [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Интерфейсы, относящиеся к связыванию данных](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)