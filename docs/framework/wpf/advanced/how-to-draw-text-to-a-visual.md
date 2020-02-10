---
title: Практическое руководство. Рисование текста в визуальном элементе
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094557"
---
# <a name="how-to-draw-text-to-a-visual"></a>Практическое руководство. Рисование текста в визуальном элементе
В следующем примере показано, как нарисовать текст в <xref:System.Windows.Media.DrawingVisual> с помощью объекта <xref:System.Windows.Media.DrawingContext>. Контекст рисования возвращается путем вызова метода <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> объекта <xref:System.Windows.Media.DrawingVisual>. Рисунки и текст можно рисовать в контексте рисования.  
  
 Чтобы нарисовать текст в контексте рисования, используйте метод <xref:System.Windows.Media.DrawingContext.DrawText%2A> объекта <xref:System.Windows.Media.DrawingContext>. Завершив рисование содержимого в контексте рисования, вызовите метод <xref:System.Windows.Media.DrawingContext.Close%2A>, чтобы закрыть контекст рисования и сохранить содержимое.  
  
## <a name="example"></a>Пример  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).
