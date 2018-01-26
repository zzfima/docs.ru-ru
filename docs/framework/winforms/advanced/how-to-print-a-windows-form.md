---
title: "Практическое руководство. Печать формы Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c50b1f47d207334160ed12674ee8efb1390fb84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-print-a-windows-form"></a>Практическое руководство. Печать формы Windows Forms
В рамках процесса разработки обычно требуется распечатать копию формы Windows Forms. В следующем примере кода показано, как напечатать копию текущей формы с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Это полный пример кода, содержащий `Main` метод.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   У вас разрешения на доступ к принтеру.  
  
-   Нет не установлен принтер.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы запустить этот пример кода, необходимо иметь разрешение на доступ к принтеру, используемому на компьютере.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Практическое руководство. Прорисовка изображений с использованием GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [Практическое руководство. Печать графических изображений в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
