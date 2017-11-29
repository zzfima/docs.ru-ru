---
title: "Построение и рисование кривых"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 801af10f7b9e5e7998fc061537977c5bced6bdb3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="constructing-and-drawing-curves"></a>Построение и рисование кривых
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]поддерживает различные типы кривых: эллипсы, дуги, фундаментальные сплайны и сплайнов Безье. Эллипс определяется его ограничивающего прямоугольника; дуга является частью эллипса, определяемого, начального угла и угла поворота. Фундаментальный сплайн определяется массивом точек и параметром натяжения: гладкая кривая проходит через все точки массива, а параметр натяжения влияет на изгиб кривой. Сплайн Безье определяется двумя конечными точками и двумя контрольными точками кривая не проходит через контрольные точки, но контрольные точки, влияют на и форму кривой переходит от одной конечной точки в другую.  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Рисование фундаментальных сплайнов](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 Описывает фундаментальные сплайны и способов их рисования.  
  
 [Практическое руководство. Рисование отдельного сплайна Безье](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 Описание сплайнов Безье и способов их рисования.  
  
 [Практическое руководство. Рисование последовательности сплайнов Безье](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 Объясняется, как рисование нескольких последовательных сплайнов Безье в последовательности.
