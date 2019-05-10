---
title: Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210393"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms

Хотя в конструкторе Windows Forms в Visual Studio оптимизирована для размещения элементов управления Windows Forms, также можно поместить элементы управления ActiveX в формах Windows Forms.

> [!CAUTION]
> Существуют ограничения производительности для Windows Forms, когда к ним добавляются элементы управления ActiveX.

Чтобы добавить элементы управления ActiveX в форму, их необходимо добавить на панель элементов. Дополнительные сведения см. в разделе [COM-компонентов, элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).

## <a name="add-an-activex-control-to-your-windows-form"></a>Добавление элемента управления ActiveX в форму Windows

Чтобы добавить элемент управления ActiveX в форму Windows, дважды щелкните элемент управления на панели элементов.

Visual Studio добавляет все ссылки на элемент управления в проекте. Дополнительные сведения о том, что следует учитывать при использовании элементов управления ActiveX в формах Windows Forms, см. в разделе [вопросы размещения элемента управления ActiveX в Windows Forms](considerations-when-hosting-an-activex-control-on-a-windows-form.md).

> [!NOTE]
> Импорта элемента управления ActiveX Windows Forms (AxImp.exe) создает аргументы события другого типа, чем требуется при импортировании библиотек динамической компоновки ActiveX. Аргументы, создаваемые по AxImp.exe, аналогичную следующей: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` ожидается. Имейте в виду, что это нарушение правил не мешает код работает нормально. Дополнительные сведения см. в разделе [Windows программа импорта элементов ActiveX форм (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Практическое руководство. Добавление элементов управления Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Упорядочение элементов управления в формах Windows Forms](arranging-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
