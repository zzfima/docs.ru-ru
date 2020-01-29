---
title: Установка фона панели с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731921"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Как задать фон панели Windows Forms с помощью конструктора

Элемент управления Windows Forms <xref:System.Windows.Forms.Panel> может отображать как цвет фона, так и фоновое изображение. Свойство <xref:System.Windows.Forms.Control.BackColor%2A> задает цвет фона для элементов управления, содержащихся на панели, таких как метки и переключатели. Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> не задано, выбор <xref:System.Windows.Forms.Control.BackColor%2A> будет заполнять все панели. Если задано свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A>, изображение будет отображаться позади элементов управления, содержащихся на панели.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.Panel>. Сведения о том, как настроить такой проект в Visual Studio, см. в разделе [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Задайте фон в конструктор Windows Forms

1. Откройте проект в Visual Studio и выберите элемент управления <xref:System.Windows.Forms.Panel>.

2. В окне **Свойства** нажмите кнопку со стрелкой рядом со свойством <xref:System.Windows.Forms.Control.BackColor%2A>, чтобы отобразить окно с тремя вкладками.

3. Выберите вкладку **Пользовательская** , чтобы отобразить палитру цветов.

4. Перейдите на вкладку **веб** или **система** , чтобы отобразить список предопределенных имен цветов, а затем выберите цвет.

5. В окне **Свойства** нажмите кнопку со стрелкой рядом со свойством <xref:System.Windows.Forms.Control.BackgroundImage%2A>.

6. В диалоговом окне **Открыть** выберите файл, который требуется отобразить.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Элемент управления Panel](panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
- [Практическое руководство. Группирование элементов управления с элементом управления Panel в формах Windows Forms с помощью конструктора](group-controls-with-wf-panel-control-using-the-designer.md)
