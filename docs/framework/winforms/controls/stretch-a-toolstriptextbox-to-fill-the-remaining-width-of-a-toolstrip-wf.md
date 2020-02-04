---
title: Практическое руководство. Растягивание ToolStripTextBox для заполнения оставшегося пространства элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742837"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Практическое руководство. Растягивание ToolStripTextBox для заполнения оставшегося пространства элемента управления ToolStrip (Windows Forms)
Если для свойства <xref:System.Windows.Forms.ToolStrip.Stretch%2A> элемента управления <xref:System.Windows.Forms.ToolStrip> задано значение `true`, элемент управления заполняет его контейнер от сквозного к концу и изменяет размеры при изменении размера контейнера. В такой конфигурации может оказаться полезным растяжение элемента в элементе управления, например <xref:System.Windows.Forms.ToolStripTextBox>, для заполнения доступного пространства и изменения размера при изменении размера элемента управления. Такое растяжение полезно, например, если требуется обеспечить внешний вид и поведение, аналогичные адресной строке в Microsoft® Internet Explorer.  
  
## <a name="example"></a>Пример  
 В следующем примере кода представлен класс, производный от <xref:System.Windows.Forms.ToolStripTextBox> с именем `ToolStripSpringTextBox`. Этот класс переопределяет метод <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>, чтобы вычислить доступную ширину родительского элемента управления <xref:System.Windows.Forms.ToolStrip> после вычитания общей ширины всех остальных элементов. Этот пример кода также предоставляет класс <xref:System.Windows.Forms.Form> и класс `Program` для демонстрации нового поведения.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
