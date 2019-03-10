---
title: Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 3d4112d87dbd448c7e34d2b84d11b49f56e1dc44
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713349"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора
*Ключ доступа* , подчеркивается в тексте элемента меню, пункт меню или метка элемента управления, такого как кнопка. Он позволяет пользователю «click» кнопки с помощью клавиши ALT и клавишу с буквой. Например, если кнопка запускает процесс печати формы и поэтому его `Text` свойство имеет значение «Print», добавив символ амперсанда (&) перед буквой «P» буква «P» быть подчеркнуты в тексте кнопки во время выполнения. Пользователь может выполнять команда, связанная с кнопкой, нажав клавиши ALT + P. Не может иметь ключ доступа для элемента управления, который не может получить фокус.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Чтобы создать ключ доступа для элемента управления  
  
1.  В **свойства** окне `Text` свойство на строку, которая включает знак амперсанда (&) перед буквой, которая будет использоваться ключ доступа. Например, чтобы задать буква «P» как клавиша доступа, введите **& Печать** в сетку.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Button>
- [Практическое руководство. Ответ на нажатие кнопки Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Задать текст, отображаемый элементом управления форм Windows](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
