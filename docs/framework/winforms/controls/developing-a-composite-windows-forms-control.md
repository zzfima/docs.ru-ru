---
title: Разработка составного элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: d80564c71dad57ce9145fbedd45a1396df1ddfec
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746028"
---
# <a name="develop-a-composite-windows-forms-control"></a>Разработка составного элемента управления Windows Forms

Можно разработать составной элемент управления Windows Forms, объединив другие элементы управления Windows Forms. Составные элементы управления, производные от <xref:System.Web.UI.UserControl>, называются пользовательскими. Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает маршрутизацию событий клавиатуры для дочерних элементов управления, это гарантирует, что дочерние элементы управления смогут получать фокус ввода. Пример пользовательского элемента управления см. в <xref:System.Windows.Forms.UserControl> образце [руководства по применению атрибутов в Windows Formsных](how-to-apply-attributes-in-windows-forms-controls.md)элементах управления.

Конструктор Windows Forms в Visual Studio обеспечивает широкую поддержку во время разработки для разработки пользовательских элементов управления.

- [Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)

- [Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual C#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [Практическое руководство. Наследование существующих элементов управления Windows Forms](how-to-inherit-from-existing-windows-forms-controls.md)

- [Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [Практическое руководство. Наследование класса Control](how-to-inherit-from-the-control-class.md)

- [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [Практическое руководство. Наследование класса UserControl](how-to-inherit-from-the-usercontrol-class.md)

- [Практическое руководство. Создание элементов управления для форм Windows Forms](how-to-author-controls-for-windows-forms.md)

- [Практическое руководство. Создание составных элементов управления](how-to-author-composite-controls.md)

- [Пример. Создание составного элемента управления с помощью C#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки](creating-a-wf-control-design-time-features.md)

- [Практическое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций, применяемых во время разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))

## <a name="see-also"></a>См. также:

- [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md)
- [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)
- [Разновидности пользовательских элементов управления](varieties-of-custom-controls.md)
