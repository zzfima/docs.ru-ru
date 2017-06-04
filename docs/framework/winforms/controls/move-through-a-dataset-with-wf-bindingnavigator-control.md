---
title: "Практическое руководство. Перемещение по набору данных с помощью элемента управления BindingNavigator в Windows Forms | Microsoft Docs"
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
  - "BindingNavigator - элемент управления [Windows Forms], перемещение по наборам данных"
  - "наборы данных [Windows Forms], перемещение по"
  - "примеры [Windows Forms], BindingNavigator - элемент управления"
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Перемещение по набору данных с помощью элемента управления BindingNavigator в Windows Forms
При создании управляемых данными приложений часто необходимо показывать коллекции данных пользователям.  Элемент управления <xref:System.Windows.Forms.BindingNavigator> в сочетании с компонентом <xref:System.Windows.Forms.BindingSource> обеспечивает удобное и расширяемое решение для перемещения по коллекции и последовательного отображения элементов.  
  
## Пример  
 В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.BindingNavigator> для перемещения по данным.  Набор содержится в элементе <xref:System.Data.DataView>, который привязан к элементу управления <xref:System.Windows.Forms.TextBox> с компонентом <xref:System.Windows.Forms.BindingSource>.  
  
> [!NOTE]
>  Хранение конфиденциальных сведений \(например, пароля\) в строке подключения может повлиять на безопасность приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Подробнее см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing, System.Windows.Forms и System.Xml.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)