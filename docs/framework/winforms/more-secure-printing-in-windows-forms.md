---
title: "More Secure Printing in Windows Forms | Microsoft Docs"
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
  - "PrintingPermission class, Windows Forms security"
  - "printing [Windows Forms], security"
  - "security [Windows Forms], printing"
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# More Secure Printing in Windows Forms
В приложениях Windows Forms часто предусмотрена возможность печати.  В среде [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] используется класс <xref:System.Drawing.Printing.PrintingPermission> для управления доступом к возможностям печати и связанные значения перечисления <xref:System.Drawing.Printing.PrintingPermissionLevel> для указания уровня доступа.  По умолчанию печать включена в зонах локальной сети и Интернета, однако уровень доступа ограничен в обеих зонах.  От разрешения, предоставленного приложению, зависит, разрешена ли печать из этого приложения и требуется ли взаимодействие с пользователем.  По умолчанию зона локальной интрасети получает уровень доступа <xref:System.Drawing.Printing.PrintingPermissionLevel>, а зона Интернета — уровень доступа <xref:System.Drawing.Printing.PrintingPermissionLevel>.  
  
 В следующей таблице показано, какие функциональные возможности доступны на каждом уровне разрешения на печать.  
  
|PrintingPermissionLevel|Описание|  
|-----------------------------|--------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Предоставляет полный доступ ко всем установленным принтерам|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Делает возможной программную печать на принтере по умолчанию и более безопасную печать через диалоговое окно печати.  <xref:System.Drawing.Printing.PrintingPermissionLevel> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Предоставляет возможность печати только из более ограниченного диалогового окна.  <xref:System.Drawing.Printing.PrintingPermissionLevel> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Предотвращает доступ к принтерам.  <xref:System.Drawing.Printing.PrintingPermissionLevel> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
  
## См. также  
 [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [Additional Security Considerations in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)   
 [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Windows Forms Security](../../../docs/framework/winforms/windows-forms-security.md)