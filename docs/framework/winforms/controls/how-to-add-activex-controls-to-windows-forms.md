---
title: Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 8c4c6c3f96c49401b032e360314794cc800c0551
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987058"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms

Хотя конструктор Windows Forms в Visual Studio оптимизированы для размещения элементов управления Windows Forms, можно также разместить элементы управления ActiveX на Windows Forms.

> [!CAUTION]
> При добавлении элементов управления ActiveX к ним применяются ограничения производительности Windows Forms.

Перед добавлением элементов управления ActiveX в форму их необходимо добавить на панель элементов. Дополнительные сведения см. в разделе [компоненты COM, диалоговое окно "Настройка панели элементов"](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).

## <a name="add-an-activex-control-to-your-windows-form"></a>Добавление элемента управления ActiveX в форму Windows Forms

Чтобы добавить элемент управления ActiveX в форму Windows, дважды щелкните элемент управления на панели элементов.

Visual Studio добавляет все ссылки на элемент управления в проекте. Дополнительные сведения о том, что следует помнить при использовании элементов управления ActiveX в Windows Forms, см. в разделе [рекомендации при размещении элемента управления ActiveX в форме Windows Forms](considerations-when-hosting-an-activex-control-on-a-windows-form.md).

> [!NOTE]
> Windows Forms импортера элемента управления ActiveX (AxImp. exe) создает аргументы события другого типа, чем ожидалось при импорте библиотек динамической компоновки ActiveX. Аргументы, созданные программой AxImp. exe, похожи на следующие: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` ожидается. Имейте в виду, что такая нерегулярность не мешает нормальному функционированию кода. Дополнительные сведения см. в разделе [Windows Forms средство импорта элементов управления ActiveX (AxImp. exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
