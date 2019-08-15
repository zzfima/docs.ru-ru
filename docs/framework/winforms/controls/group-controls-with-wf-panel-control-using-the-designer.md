---
title: Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: cadfa715b140c63b216ec0ca2e6d6a6589ae3458
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040390"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора
Элементы <xref:System.Windows.Forms.Panel> управления Windows Forms используются для группирования других элементов управления. Существует три причины для группировки элементов управления. Одна из них — визуальное группирование связанных элементов формы для простого пользовательского интерфейса; другой — программное группирование, например, переключатели. Последний — перемещение элементов управления как единицы во время разработки.

## <a name="to-create-a-group-of-controls"></a>Создание группы элементов управления

1. Перетащите элемент управления с вкладки Windows Forms панели элементов на форму. <xref:System.Windows.Forms.Panel>

2. Добавьте на панель другие элементы управления, рисуя их внутри панели.

     Если у вас есть элементы управления, которые необходимо заключить в панель, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать <xref:System.Windows.Forms.Panel> элемент управления и вставить их на панель. Их также можно перетащить на панель.

3. Используемых Если вы хотите добавить на панель границу, задайте ее <xref:System.Windows.Forms.BorderStyle> свойство. Существует три варианта выбора: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>и <xref:System.Windows.Forms.BorderStyle.None>.

## <a name="see-also"></a>См. также

- [Элемент управления Panel](panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
- [Практическое руководство. Настройка фона панели](how-to-set-the-background-of-a-windows-forms-panel.md)
