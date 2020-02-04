---
title: Группирование элементов управления Panel с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 927aeb5b51bc1ac4e22a45e487b49424b4e67b71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745650"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора
Windows Forms элементы управления <xref:System.Windows.Forms.Panel> используются для группирования других элементов управления. Существует три причины для группировки элементов управления. Одна из них — визуальное группирование связанных элементов формы для простого пользовательского интерфейса; другой — программное группирование, например, переключатели. Последний — перемещение элементов управления как единицы во время разработки.

## <a name="to-create-a-group-of-controls"></a>Создание группы элементов управления

1. Перетащите элемент управления <xref:System.Windows.Forms.Panel> с вкладки **Windows Forms** панели элементов на форму.

2. Добавьте на панель другие элементы управления, рисуя их внутри панели.

     Если у вас есть элементы управления, которые необходимо заключить в панель, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать элемент управления <xref:System.Windows.Forms.Panel> и вставить их на панель. Их также можно перетащить на панель.

3. Используемых Если вы хотите добавить на панель границу, задайте ее свойство <xref:System.Windows.Forms.BorderStyle>. Существует три варианта: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>и <xref:System.Windows.Forms.BorderStyle.None>.

## <a name="see-also"></a>См. также раздел

- [Элемент управления Panel](panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
- [Практическое руководство. Установка фона панели](how-to-set-the-background-of-a-windows-forms-panel.md)
