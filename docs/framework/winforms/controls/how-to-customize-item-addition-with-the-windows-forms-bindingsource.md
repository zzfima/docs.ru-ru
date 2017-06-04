---
title: "Практическое руководство. Настройка дополнений к элементам с помощью элемента управления BindingSource в Windows Forms | Microsoft Docs"
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
  - "элементы управления [Windows Forms], создание новых элементов управления"
  - "BindingSource-компонент [Windows Forms], настройка добавления элемента с помощью"
  - "примеры [Windows Forms], компонент BindingSource"
  - "BindingSource-компонент [Windows Forms], примеры"
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Настройка дополнений к элементам с помощью элемента управления BindingSource в Windows Forms
При использовании компонента <xref:System.Windows.Forms.BindingSource> для привязки элемента управления Windows Forms к источнику данных может потребоваться настроить создание новых элементов. Компонент <xref:System.Windows.Forms.BindingSource> упрощает эту процедуру, предоставляя событие <xref:System.Windows.Forms.BindingSource.AddingNew>, которое обычно происходит, когда связанный элемент управления должен создать новый элемент. Обработчик событий может обеспечивать любое необходимое поведение \(например, вызов метода веб\-службы или получение нового объекта из фабрики класса\).  
  
> [!NOTE]
>  Добавление элемента с помощью события <xref:System.Windows.Forms.BindingSource.AddingNew> отменить нельзя.  
  
## Пример  
 В примере ниже показано, как связать элемент управления <xref:System.Windows.Forms.DataGridView> с фабрикой класса с помощью компонента <xref:System.Windows.Forms.BindingSource>. Когда пользователь щелкает новую строку элемента управления <xref:System.Windows.Forms.DataGridView>, вызывается событие <xref:System.Windows.Forms.BindingSource.AddingNew>. Обработчик событий создает объект `DemoCustomer`, который присваивается свойству <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=fullName>. В результате новый объект `DemoCustomer` добавляется к списку компонентов <xref:System.Windows.Forms.BindingSource> и отображается в новой строке элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Дополнительные сведения о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] см. в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)