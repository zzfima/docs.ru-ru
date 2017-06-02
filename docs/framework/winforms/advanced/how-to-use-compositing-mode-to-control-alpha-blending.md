---
title: "Практическое руководство. Использование режима комбинирования для управления альфа-смешением | Microsoft Docs"
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
  - "альфа-смешение, комбинирование"
  - "цвета, смешение"
  - "цвета, управление прозрачностью"
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Использование режима комбинирования для управления альфа-смешением
Иногда может потребоваться создать вне экрана точечное изображение, обладающее следующими характеристиками.  
  
-   Альфа\-компоненты цветов меньше 255.  
  
-   При создании растрового изображения не выполняется альфа\-смешение цветов друг с другом.  
  
-   При выводе окончательно сформированного растрового изображения на устройстве отображения выполняется альфа\-смешение цветов точечного изображения с цветами фона.  
  
 Для формирования такого растрового изображения следует создать пустой объект <xref:System.Drawing.Bitmap>, а затем построить на его основе объект <xref:System.Drawing.Graphics>.  Присвойте режиму комбинирования объекта <xref:System.Drawing.Graphics> значение <xref:System.Drawing.Drawing2D.CompositingMode?displayProperty=fullName>.  
  
## Пример  
 В приведенном ниже примере создается объект <xref:System.Drawing.Graphics> на основе объекта <xref:System.Drawing.Bitmap>.  Объект <xref:System.Drawing.Graphics> используется в коде вместе с двумя полупрозрачными кистями \(альфа\-компонент равен 160\) для рисования на фоне растрового изображения.  В примере осуществляется заливка красного и зеленого эллипсов с помощью полупрозрачных кистей.  Зеленый эллипс частично перекрывается с красным эллипсом, но зеленый и красный цвета не смешиваются, потому что режим комбинирования, принадлежащий объекту <xref:System.Drawing.Graphics>, установлен равным <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 Растровое изображение рисуется на экране дважды: один раз на белом фоне, а другой раз на многоцветном фоне.  Пиксели растрового изображения, являющиеся частями двух ранее нарисованных эллипсов, имеют альфа\-компонент, равный 160, поэтому цвета эллипсов смешиваются с фоновыми цветами на экране.  
  
 На следующем рисунке показан результат выполнения примера кода.  Обратите внимание, что цвета эллипсов смешиваются с фоном, но не смешиваются друг с другом.  
  
 ![Копия источника](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 Пример кода содержит следующую инструкцию:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Если требуется, чтобы цвета эллипсов смешивались друг с другом так же, как и с фоном, замените эту инструкцию на приведенную ниже.  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 На следующем рисунке показан результат выполнения измененного кода.  
  
 ![Источник над](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [Альфа\-смешение цвета для линий и заливок](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)