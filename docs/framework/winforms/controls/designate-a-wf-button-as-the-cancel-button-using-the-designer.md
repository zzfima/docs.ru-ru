---
title: Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039650"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора
В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> элемент управления кнопкой Отмена. Нажатие кнопки «отмена» происходит каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, какой элемент управления формы имеет фокус. Такая кнопка обычно запрограммирована, позволяя пользователю быстро выйти из операции без фиксации каких-либо действий.

## <a name="to-designate-the-cancel-button"></a>Назначение кнопки «Отмена»

1. Выберите форму, в которой находится кнопка.

2. В окне **Свойства** задайте для <xref:System.Windows.Forms.Form.CancelButton%2A> <xref:System.Windows.Forms.Button> свойства формы имя элемента управления.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Реакция на нажатие кнопки Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Назначение кнопки Windows Forms в качестве кнопки Accept с помощью конструктора](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Элемент управления Button](button-control-windows-forms.md)
