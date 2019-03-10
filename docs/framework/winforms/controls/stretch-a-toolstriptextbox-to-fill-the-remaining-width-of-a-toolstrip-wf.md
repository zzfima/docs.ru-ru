---
title: Практическое руководство. Растягивание ToolStripTextBox пространства для заполнения оставшегося элемента управления ToolStrip (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 7a557a3d278c2b6d8d083b2ebf8c8129bc498afa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702767"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Практическое руководство. Растягивание ToolStripTextBox пространства для заполнения оставшегося элемента управления ToolStrip (Windows Forms)
При задании <xref:System.Windows.Forms.ToolStrip.Stretch%2A> свойство <xref:System.Windows.Forms.ToolStrip> управления `true`, элемент управления заполняет контейнер от начала до конца и изменяет размер при изменении размеров контейнера. В этой конфигурации могут оказаться полезными для растяжения элемента в элементе управления, такие как <xref:System.Windows.Forms.ToolStripTextBox>, чтобы заполнить доступное пространство, так и для изменения размера при изменении размера элемента управления. Таком растягивании полезно, например, если требуется обеспечить внешний вид и поведение, аналогичное в адресную строку обозревателя Microsoft® Internet Explorer.  
  
## <a name="example"></a>Пример  
 В следующем примере кода предоставляет класс, производный от <xref:System.Windows.Forms.ToolStripTextBox> вызывается `ToolStripSpringTextBox`. Этот класс переопределяет <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> для расчета доступную ширину родительского <xref:System.Windows.Forms.ToolStrip> управления после вычитания объединенный ширину всех элементов. Этот пример кода также предоставляет <xref:System.Windows.Forms.Form> класса и `Program` для демонстрации нового поведения.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
