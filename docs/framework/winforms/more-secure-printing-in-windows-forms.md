---
title: "Более безопасная печать в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f36ee150e4dcca74141b644a55451abd4a4fd21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="more-secure-printing-in-windows-forms"></a>Более безопасная печать в Windows Forms
Приложения Windows Forms часто предусмотрена возможность печати. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Использует <xref:System.Drawing.Printing.PrintingPermission> класса для управления доступом к возможностям печати и связанное с ним <xref:System.Drawing.Printing.PrintingPermissionLevel> значение перечисления, указывающее уровень доступа. По умолчанию печать включена по умолчанию в зонах локальной интрасети и Интернета; Однако уровень доступа ограничен в обеих зонах. Ли печать из этого приложения, требует взаимодействия с пользователем, или не может печати зависит от разрешения, предоставленного в приложение. По умолчанию зона локальной интрасети получает <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> получает доступ и интрасеть <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> доступа.  
  
 В следующей таблице показаны функциональные возможности, доступные на каждой печати уровне разрешений.  
  
|PrintingPermissionLevel|Описание:|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Предоставляет полный доступ для всех установленных принтеров.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Позволяет программную печать на принтере по умолчанию и более безопасную печать через диалоговое окно печати. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Предоставляет возможность печати только из более ограниченного диалоговым окном. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Запрещает доступ к принтерам. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>См. также  
 [Более безопасный доступ к файлам и данным в Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Дополнительные вопросы безопасности в формах Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [Общие сведения о безопасности в Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Безопасность Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)
