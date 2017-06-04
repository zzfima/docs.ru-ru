---
title: "Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms | Microsoft Docs"
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
  - "ввод данных, обработка ошибок"
  - "таблицы данных, обработка ошибок"
  - "DataGridView - элемент управления [Windows Forms], обработка ошибок"
  - "обработка ошибок, ввод данных"
  - "обработка ошибок, DataGridView - элемент управления"
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms
В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.DataGridView> для сообщения пользователю об ошибках ввода данных.  
  
 Полное описание этого примера кода см. в разделе [Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Windows.Forms и System.XML.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Безопасность платформы .NET Framework  
 Хранение конфиденциальных сведений \(например, пароля\) в строке подключения может повлиять на безопасность приложений.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Подробнее см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Пример. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)