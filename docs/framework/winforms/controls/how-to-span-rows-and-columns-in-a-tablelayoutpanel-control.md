---
title: Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039698"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
<xref:System.Windows.Forms.TableLayoutPanel> Элементы управления могут охватывать смежные строки и столбцы.

## <a name="to-span-columns-and-rows"></a>Охват столбцов и строк

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. Перетащите элемент управления из **области элементов** в верхнюю <xref:System.Windows.Forms.TableLayoutPanel> левую ячейку элемента управления. <xref:System.Windows.Forms.Button>

3. Задайте для свойства **ColumnSpan** элементауправлениязначение<xref:System.Windows.Forms.Button> 2. Обратите внимание <xref:System.Windows.Forms.Button> , что элемент управления охватывает первый и второй столбцы.

4. Присвойте свойству **RowSpan** элементауправлениязначение<xref:System.Windows.Forms.Button> 2. Обратите внимание <xref:System.Windows.Forms.Button> , что элемент управления охватывает первую и вторую строки.

5. Задайте для свойства **ColumnSpan** элементауправлениязначение<xref:System.Windows.Forms.Button> 1. Обратите внимание <xref:System.Windows.Forms.Button> , что элемент управления перемещается в первый столбец и охватывает первую и вторую строки.

## <a name="see-also"></a>См. также

- [Элемент управления TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
