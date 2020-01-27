---
title: Назначение кнопки "Отмена" с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746048"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора
В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button> в качестве кнопки отмены. Нажатие кнопки «отмена» происходит каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, какой элемент управления формы имеет фокус. Такая кнопка обычно запрограммирована, позволяя пользователю быстро выйти из операции без фиксации каких-либо действий.

## <a name="to-designate-the-cancel-button"></a>Назначение кнопки «Отмена»

1. Выберите форму, в которой находится кнопка.

2. В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Form.CancelButton%2A> формы имя элемента управления <xref:System.Windows.Forms.Button>.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Элемент управления Button](button-control-windows-forms.md)
