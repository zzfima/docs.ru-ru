---
title: Более безопасная печать
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734891"
---
# <a name="more-secure-printing-in-windows-forms"></a>Более безопасная печать в Windows Forms
Windows Forms приложения часто включают возможности печати. .NET Framework использует класс <xref:System.Drawing.Printing.PrintingPermission> для управления доступом к возможностям печати и связанным значением перечисления <xref:System.Drawing.Printing.PrintingPermissionLevel>, чтобы указать уровень доступа. По умолчанию печать по умолчанию включена в зонах «Местная интрасеть» и «Интернет». Однако уровень доступа ограничен в обеих зонах. Может ли приложение печататься, требует взаимодействия с пользователем или не может печататься, зависит от значения разрешений, предоставленного приложению. По умолчанию зона локальной интрасети получает <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> доступ, а зона интрасети — <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> доступ.  
  
 В следующей таблице показаны функциональные возможности, доступные для каждого уровня разрешений печати.  
  
|PrintingPermissionLevel|Описание|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Предоставляет полный доступ ко всем установленным принтерам.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Разрешает программную печать на принтере по умолчанию и более безопасную печать через диалоговое окно с ограниченным режимом печати. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Предоставляет печать только из более ограниченного диалогового окна. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Предотвращает доступ к принтерам. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>См. также:

- [Более безопасный доступ к файлам и данным в Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Дополнительные вопросы безопасности в формах Windows Forms](additional-security-considerations-in-windows-forms.md)
- [Общие сведения о безопасности в Windows Forms](security-in-windows-forms-overview.md)
- [Безопасность Windows Forms](windows-forms-security.md)
