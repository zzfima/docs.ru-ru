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
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963850"
---
# <a name="how-to-draw-text-to-a-visual"></a>Практическое руководство. Рисование текста в визуальном элементе
В следующем примере показано, как нарисовать текст в <xref:System.Windows.Media.DrawingVisual> с <xref:System.Windows.Media.DrawingContext> помощью объекта. Контекст рисования возвращается путем вызова <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> метода <xref:System.Windows.Media.DrawingVisual> объекта. Рисунки и текст можно рисовать в контексте рисования.  
  
 Чтобы нарисовать текст в контексте рисования, используйте <xref:System.Windows.Media.DrawingContext.DrawText%2A> метод <xref:System.Windows.Media.DrawingContext> объекта. Завершив рисование содержимого в контексте рисования, вызовите <xref:System.Windows.Media.DrawingContext.Close%2A> метод, чтобы закрыть контекст рисования и сохранить содержимое.  
  
## <a name="example"></a>Пример  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).
