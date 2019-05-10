---
title: Практическое руководство. Обрезка изображения по границам области обрезки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063841"
---
# <a name="how-to-use-clipping-with-a-region"></a>Практическое руководство. Обрезка изображения по границам области обрезки
Одно из свойств объекта <xref:System.Drawing.Graphics> класс является отсеченную область. Все операции рисования, выполняемые заданного <xref:System.Drawing.Graphics> объекта будет ограничен отсеченную область объекта, <xref:System.Drawing.Graphics> объекта. Можно задать отсеченную область, вызвав <xref:System.Drawing.Graphics.SetClip%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере создается путь, состоящий из одного многоугольника. Затем код создает область, на основе этого пути. Область передается <xref:System.Drawing.Graphics.SetClip%2A> метод <xref:System.Drawing.Graphics> рисовании объекта и затем две строки.  
  
 На следующем рисунке показан усеченные строки:  
  
 ![Снимок экрана, показывающий усеченные строки.](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также

- [Области в GDI+](regions-in-gdi.md)
- [Использование областей](using-regions.md)
