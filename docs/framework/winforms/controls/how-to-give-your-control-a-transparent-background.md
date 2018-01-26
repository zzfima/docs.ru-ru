---
title: "Практическое руководство. Установка степени прозрачности фона элемента управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab2a8562401561cfb2a54d4630e32bf7527da10d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Практическое руководство. Установка степени прозрачности фона элемента управления
В предыдущих версиях платформы .NET Framework элементы управления не поддерживали задание прозрачных цветов фона, если предварительно не был установлен метод <xref:System.Windows.Forms.Control.SetStyle%2A> в конструкторе форм. В текущей версии платформы для большинства элементов управления можно задать цвет фона <xref:System.Drawing.Color.Transparent%2A> в окне **Свойства** во время разработки или в коде в конструкторе форм.  
  
> [!NOTE]
>  Элементы управления Windows Forms не поддерживают настоящую прозрачность. Фон прозрачного элемента управления Windows Forms закрашивается его родительским элементом.  
  
> [!NOTE]
>  Элемент управления <xref:System.Windows.Controls.Button> не поддерживает прозрачный цвет фона, даже если свойство <xref:System.Windows.Forms.ButtonBase.BackColor%2A> имеет значение <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Установка прозрачного фона для элемента управления  
  
-   В окне "Свойства" выберите свойство <xref:System.Windows.Forms.ButtonBase.BackColor%2A> и задайте ему значение <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [Практическое руководство. Рисование непрозрачных и полупрозрачных линий](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
