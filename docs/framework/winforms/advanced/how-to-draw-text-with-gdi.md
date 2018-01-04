---
title: "Практическое руководство. Рисование текста с использованием GDI"
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
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6c7fb4d8c6bd93481935a9f2ef7dd4b34af7e71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-with-gdi"></a>Практическое руководство. Рисование текста с использованием GDI
С <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод в <xref:System.Windows.Forms.TextRenderer> класс, доступны [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] функциональные возможности для рисования текста в форме или элементе управления. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]визуализация текста обычно обладают большей производительностью и более точно управляют параметрами чем текста [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Методы <xref:System.Windows.Forms.TextRenderer> класса не поддерживаются для печати. При печати, всегда используйте <xref:System.Drawing.Graphics.DrawString%2A> методы <xref:System.Drawing.Graphics> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как отображается текст на нескольких строках внутри прямоугольника с помощью <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Чтобы отобразить с <xref:System.Windows.Forms.TextRenderer> класса, необходимо <xref:System.Drawing.IDeviceContext>, такие как <xref:System.Drawing.Graphics> и <xref:System.Drawing.Font>, расположение для рисования текста и цвет, в котором оно должно отображаться. При необходимости можно указать текст, форматирование с использованием <xref:System.Windows.Forms.TextFormatFlags> перечисления.  
  
 Дополнительные сведения о получении <xref:System.Drawing.Graphics>, в разделе [как: Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). Дополнительные сведения о построении <xref:System.Drawing.Font>, в разделе [как: шрифтов и их семейств создания](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
