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
ms.openlocfilehash: b89a94fd0223d817b0dee37f7a3ed84dcbacbbec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="e4394-102">Более безопасная печать в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4394-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="e4394-103">Приложения Windows Forms часто предусмотрена возможность печати.</span><span class="sxs-lookup"><span data-stu-id="e4394-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="e4394-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Использует <xref:System.Drawing.Printing.PrintingPermission> класса для управления доступом к возможностям печати и связанное с ним <xref:System.Drawing.Printing.PrintingPermissionLevel> значение перечисления, указывающее уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="e4394-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="e4394-105">По умолчанию печать включена по умолчанию в зонах локальной интрасети и Интернета; Однако уровень доступа ограничен в обеих зонах.</span><span class="sxs-lookup"><span data-stu-id="e4394-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="e4394-106">Ли печать из этого приложения, требует взаимодействия с пользователем, или не может печати зависит от разрешения, предоставленного в приложение.</span><span class="sxs-lookup"><span data-stu-id="e4394-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="e4394-107">По умолчанию зона локальной интрасети получает <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> получает доступ и интрасеть <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> доступа.</span><span class="sxs-lookup"><span data-stu-id="e4394-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="e4394-108">В следующей таблице показаны функциональные возможности, доступные на каждой печати уровне разрешений.</span><span class="sxs-lookup"><span data-stu-id="e4394-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="e4394-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="e4394-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="e4394-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e4394-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="e4394-111">Предоставляет полный доступ для всех установленных принтеров.</span><span class="sxs-lookup"><span data-stu-id="e4394-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="e4394-112">Позволяет программную печать на принтере по умолчанию и более безопасную печать через диалоговое окно печати.</span><span class="sxs-lookup"><span data-stu-id="e4394-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="e4394-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span><span class="sxs-lookup"><span data-stu-id="e4394-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="e4394-114">Предоставляет возможность печати только из более ограниченного диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="e4394-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="e4394-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span><span class="sxs-lookup"><span data-stu-id="e4394-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="e4394-116">Запрещает доступ к принтерам.</span><span class="sxs-lookup"><span data-stu-id="e4394-116">Prevents access to printers.</span></span> <span data-ttu-id="e4394-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> является подмножеством <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span><span class="sxs-lookup"><span data-stu-id="e4394-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4394-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e4394-118">See Also</span></span>  
 [<span data-ttu-id="e4394-119">Более безопасный доступ к файлам и данным в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4394-119">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [<span data-ttu-id="e4394-120">Дополнительные вопросы безопасности в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4394-120">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="e4394-121">Общие сведения о безопасности в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4394-121">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="e4394-122">Безопасность Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4394-122">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)
