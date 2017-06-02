---
title: "Значение порядка преобразований | Microsoft Docs"
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
  - "преобразования, значимость порядка"
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Значение порядка преобразований
В одном объекте <xref:System.Drawing.Drawing2D.Matrix> может храниться одно преобразование или некоторая последовательность преобразований.  Такая последовательность преобразований называется составным преобразованием.  Матрица составного преобразования получается с помощью перемножения матриц отдельных преобразований.  
  
## Примеры составных преобразований  
 Порядок следования отдельных преобразований имеет важное значение для составного преобразования.  Например, если применяется поворот, затем масштабирование, а затем сдвиг, получается совершенно другой результат, чем если бы сначала был применен сдвиг, затем поворот, а затем масштабирование.  В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] построение составных преобразований осуществляется слева направо.  Если S, R и T являются матрицами масштабирования, поворота и сдвига, соответственно, тогда произведение SRT \(именно в таком порядке\) является матрицей составного преобразования, которое сначала масштабирует, затем поворачивает, а затем осуществляет сдвиг.  Матрица, равная произведению SRT, отличается от матрицы, являющейся произведением TRS.  
  
 Одной из причин важности порядка выполнения преобразований является то, что такие преобразования, как поворот и масштабирование, осуществляются относительно начала координат.  Масштабирование объекта, центрированного по началу координат, дает другой результат, чем масштабирование объекта, который куда\-либо сдвинут относительно этой точки.  Аналогично, поворот объекта, центрированного по началу координат, дает другой результат, чем поворот объекта, который куда\-либо сдвинут относительно этой точки.  
  
 В следующем примере комбинация масштабирования, поворота и сдвига \(именно в таком порядке\) используется для конструирования составного преобразования.  Аргумент <xref:System.Drawing.Drawing2D.MatrixOrder>, передаваемый методу <xref:System.Drawing.Graphics.RotateTransform%2A>, указывает на то, что поворот будет выполняться после масштабирования.  Аналогично аргумент <xref:System.Drawing.Drawing2D.MatrixOrder>, передаваемый методу <xref:System.Drawing.Graphics.TranslateTransform%2A>, указывает на то, что сдвиг будет выполняться после поворота.  <xref:System.Drawing.Drawing2D.MatrixOrder> и <xref:System.Drawing.Drawing2D.MatrixOrder> являются членами перечисления <xref:System.Drawing.Drawing2D.MatrixOrder>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 В следующем примере осуществляются те же вызовы методов, что и в предыдущем, но порядок вызова методов меняется на обратный.  Получающееся при этом составное преобразование \(сдвиг, поворот, масштабирование\) дает результат, принципиально отличающийся от результата выполнения исходного преобразования \(масштабирование, поворот, сдвиг\).  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Первым способом изменения порядка выполнения отдельных преобразований, формирующих составное преобразование, на обратный является изменение на обратный порядка вызовов методов.  Второй способ управления порядком операций заключается в изменении значения параметра порядка следования матриц.  Следующий пример полностью аналогичен предыдущему, но в нем параметр <xref:System.Drawing.Drawing2D.MatrixOrder> заменен на <xref:System.Drawing.Drawing2D.MatrixOrder>.  Перемножение матриц осуществляется в порядке SRT, где S, R и T являются матрицами масштабирования, поворота и сдвига соответственно.  При применении составного преобразования сначала осуществляется масштабирование, затем поворот, а затем сдвиг.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Результаты, полученные в рассмотренном примере и самом первом примере данного раздела, ничем не отличаются друг от друга.  Это объясняется тем, что были изменены на обратный как порядок вызовов методов, так и порядок выполнения умножения матриц.  
  
## См. также  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Использование преобразований в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)