---
title: Практическое руководство. Установка степени прозрачности фона элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: a82807ea3873b2217d1f05f6c720c599ea79abdd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966640"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Практическое руководство. Установка степени прозрачности фона элемента управления
В предыдущих версиях платформы .NET Framework элементы управления не поддерживали задание прозрачных цветов фона, если предварительно не был установлен метод <xref:System.Windows.Forms.Control.SetStyle%2A> в конструкторе форм. В текущей версии платформы для большинства элементов управления можно задать цвет фона <xref:System.Drawing.Color.Transparent%2A> в окне **Свойства** во время разработки или в коде в конструкторе форм.  
  
> [!NOTE]
> Элементы управления Windows Forms не поддерживают настоящую прозрачность. Фон прозрачного элемента управления Windows Forms закрашивается его родительским элементом.  
  
> [!NOTE]
> Элемент управления <xref:System.Windows.Controls.Button> не поддерживает прозрачный цвет фона, даже если свойство <xref:System.Windows.Forms.ButtonBase.BackColor%2A> имеет значение <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Установка прозрачного фона для элемента управления  
  
- В окне "Свойства" выберите свойство <xref:System.Windows.Forms.ButtonBase.BackColor%2A> и задайте ему значение <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.Color.FromArgb%2A>
- [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)
- [Использование управляемых графических классов](../advanced/using-managed-graphics-classes.md)
- [Практическое руководство. Рисование непрозрачных и полупрозрачных линий](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
