---
title: Как выполнить Добавление элементов управления ActiveX в формы Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 2fa5d81c196e1730eafb177b20b5cba64b2daae1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721153"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Как выполнить Добавление элементов управления ActiveX в формы Windows Forms
Хотя в конструкторе Windows Forms оптимизирована для размещения элементов управления Windows Forms, также можно поместить элементы управления ActiveX в формах Windows Forms.  
  
> [!CAUTION]
>  Существуют ограничения производительности для Windows Forms, когда к ним добавляются элементы управления ActiveX.  
  
 Чтобы добавить элементы управления ActiveX в форму, их необходимо добавить на панель элементов. Дополнительные сведения см. в разделе [COM-компонентов, элементов](https://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Добавление элемента управления ActiveX в форму Windows  
  
-   Дважды щелкните элемент управления на панели элементов.  
  
     Visual Studio добавляет все ссылки на элемент управления в проекте. Дополнительные сведения о том, что следует учитывать при использовании элементов управления ActiveX в формах Windows Forms, см. в разделе [вопросы размещения элемента управления ActiveX в Windows Forms](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Импорта элемента управления ActiveX Windows Forms (AxImp.exe) создает аргументы события другого типа, чем требуется при импортировании библиотек динамической компоновки ActiveX. Аргументы, создаваемые по AxImp.exe, аналогичную следующей: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` ожидается. Имейте в виду, что это нарушение правил не мешает код работает нормально. Дополнительные сведения см. в разделе [Windows программа импорта элементов ActiveX форм (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>См. также
- [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)
- [Практическое руководство. Добавление элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
