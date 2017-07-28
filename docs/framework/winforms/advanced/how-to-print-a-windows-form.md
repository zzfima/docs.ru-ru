---
title: "How to: Print a Windows Form | Microsoft Docs"
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
  - "Windows Forms, printing"
  - "printing [Windows Forms]"
  - "printing a form"
  - "printing [Windows Forms, printing a form"
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Print a Windows Form
Обычно в процессе разработки приходится печатать копии форм Windows Forms.  В следующем примере показан способ печати копии текущей формы с помощью метода <xref:System.Drawing.Graphics.CopyFromScreen%2A>.  
  
## Пример  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Это полный пример кода, содержащего метод `Main`.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Нет разрешения на доступ к принтеру.  
  
-   Принтер не установлен.  
  
## Безопасность платформы .NET Framework  
 Чтобы запустить этот пример, необходимо иметь разрешение на доступ к принтеру, используемому на компьютере.  
  
## См. также  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Практическое руководство. Вывод изображений с использованием GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)   
 [How to: Print Graphics in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)