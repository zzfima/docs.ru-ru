---
title: Более безопасная печать в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 2bf05461014c3511725cb28caf2de0eb4c2e1d5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621803"
---
# <a name="more-secure-printing-in-windows-forms"></a>Более безопасная печать в Windows Forms
Приложения Windows Forms часто предусмотрена возможность печати. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Использует <xref:System.Drawing.Printing.PrintingPermission> класс для управления доступом к возможностям печати и связанный <xref:System.Drawing.Printing.PrintingPermissionLevel> значение перечисления, указывающее уровень доступа. По умолчанию она разрешена по умолчанию в зонах локальной интрасети и Интернета; Тем не менее в обоих зон ограничено уровень доступа. Ли приложение может начать печать, требует взаимодействия с пользователем, или не зависит значение разрешения, предоставленные приложению. По умолчанию в зону локальной интрасети получает <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> доступа и в зону интрасети получает <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> доступа.  
  
 В следующей таблице показаны функциональные возможности, доступные в каждой печати уровень разрешений.  
  
|PrintingPermissionLevel|Описание|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Предоставляет полный доступ для всех установленных принтеров.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Обеспечивает программную печать на принтере по умолчанию и более безопасную печать через диалоговое окно печати. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Предоставляет возможность печати только из более ограниченного диалоговое окно. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Запрещает доступ к принтерам. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>См. также
- [Более безопасный доступ к файлам и данным в Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)
- [Дополнительные вопросы безопасности в формах Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)
- [Общие сведения о безопасности в Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)
- [Безопасность Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)
