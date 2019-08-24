---
title: Практическое руководство. Переназначение существующих элементов управления другим родительским элементам
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987035"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Практическое руководство. Переназначить существующие элементы управления другому родителю

Можно назначать существующие в форме элементы управления новому контейнерному элементу управления.

1. В Visual Studio перетащите на форму <xref:System.Windows.Forms.Button> три элемента управления из **панели элементов** . Расположите их рядом друг с другом, но не выравнивайте.

2. В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> . (Не перетаскивайте значок на форму.)

3. Переместите указатель мыши к трем элементам управления <xref:System.Windows.Forms.Button> .

   Указатель превратится в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .

4. Нажмите и удерживайте кнопку мыши.

5. Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .

6. Обведите таким образом три элемента управления <xref:System.Windows.Forms.Button> .

7. Отпустите кнопку мыши.

   Теперь три элемента управления <xref:System.Windows.Forms.Button> вставлены в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
