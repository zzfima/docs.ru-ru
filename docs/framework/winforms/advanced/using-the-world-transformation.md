---
title: "Использование объемного преобразования"
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
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8599f2e154e05fd2d43b094041989c4a3a5dbc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-world-transformation"></a>Использование объемного преобразования
Мировое преобразование — это свойство <xref:System.Drawing.Graphics> класса. Числа, определяющие мировое преобразование хранятся в <xref:System.Drawing.Drawing2D.Matrix> объект, который представляет матрицу 3 × 3. <xref:System.Drawing.Drawing2D.Matrix> И <xref:System.Drawing.Graphics> классы имеют различные методы для установки числа в матрицу мирового преобразования.  
  
## <a name="different-types-of-transformations"></a>Различные типы преобразований  
 В следующем примере код сначала создает прямоугольник 50 × 50 и помещает его в точку начала координат (0, 0). Источником является в левом верхнем углу клиентской области.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 Следующий код применяется масштабирования преобразование, которое увеличивает прямоугольник с коэффициентом 1,75 по оси x и уменьшает прямоугольник с коэффициентом 0,5 по оси y.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Результатом является прямоугольник, который длиннее по оси x и по оси y меньше исходного.  
  
 Чтобы сменить прямоугольник вместо его масштабирования, используйте следующий код:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Чтобы преобразовать прямоугольник, используйте следующий код:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Использование преобразований в управляемом GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
