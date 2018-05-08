---
title: Практическое руководство. Печать формы Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 42940654a0754ac3616ca7983af07d20607f480f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
