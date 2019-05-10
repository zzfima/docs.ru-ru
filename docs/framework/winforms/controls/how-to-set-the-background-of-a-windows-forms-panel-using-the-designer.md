---
title: Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211633"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Практическое руководство. Меняем цвет фона панели формы Windows Forms с помощью конструктора

Windows Forms <xref:System.Windows.Forms.Panel> может отображать элемент управления цветом фона и фоновое изображение. <xref:System.Windows.Forms.Control.BackColor%2A> Свойство задает цвет фона для элементов управления, содержащихся в панели, например, метки и переключатели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не задано, <xref:System.Windows.Forms.Control.BackColor%2A> выбора будет заполнить все панели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство задано, элементы управления, содержащихся на панели отображается изображение.

Следующая процедура требуется **приложения Windows** проект с формой, содержащей <xref:System.Windows.Forms.Panel> элемента управления. Сведения о настройке такого проекта в Visual Studio, см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Задать фон в конструкторе Windows Forms

1. Откройте проект в Visual Studio и выберите <xref:System.Windows.Forms.Panel> элемента управления.

2. В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackColor%2A> свойство для отображения окна с тремя вкладками.

3. Выберите **Custom** вкладку, чтобы отобразить палитру цветов.

4. Выберите **Web** или **системы** вкладку для отображения списка предопределенных имен цветов, а затем выберите цвет.

5. В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство.

6. В **откройте** диалоговом окне выберите файл, который вы хотите отобразить.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Элемент управления Panel](panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
- [Практическое руководство. Группа элементов управления с помощью панели управления Windows Forms с помощью конструктора](group-controls-with-wf-panel-control-using-the-designer.md)
