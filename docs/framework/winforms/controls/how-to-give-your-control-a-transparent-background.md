---
title: Практическое руководство. Установка степени прозрачности фона элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 671075973793d7fbf0b70ce77428a0a632305b9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206100"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="a85a3-102">Практическое руководство. Установка степени прозрачности фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="a85a3-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="a85a3-103">В предыдущих версиях платформы .NET Framework элементы управления не поддерживали задание прозрачных цветов фона, если предварительно не был установлен метод <xref:System.Windows.Forms.Control.SetStyle%2A> в конструкторе форм.</span><span class="sxs-lookup"><span data-stu-id="a85a3-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="a85a3-104">В текущей версии платформы для большинства элементов управления можно задать цвет фона <xref:System.Drawing.Color.Transparent%2A> в окне **Свойства** во время разработки или в коде в конструкторе форм.</span><span class="sxs-lookup"><span data-stu-id="a85a3-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a85a3-105">Элементы управления Windows Forms не поддерживают настоящую прозрачность.</span><span class="sxs-lookup"><span data-stu-id="a85a3-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="a85a3-106">Фон прозрачного элемента управления Windows Forms закрашивается его родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="a85a3-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a85a3-107">Элемент управления <xref:System.Windows.Controls.Button> не поддерживает прозрачный цвет фона, даже если свойство <xref:System.Windows.Forms.ButtonBase.BackColor%2A> имеет значение <xref:System.Drawing.Color.Transparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="a85a3-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="a85a3-108">Установка прозрачного фона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="a85a3-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="a85a3-109">В окне «Свойства» выберите <xref:System.Windows.Forms.ButtonBase.BackColor%2A> свойство и присвойте ему значение</span><span class="sxs-lookup"><span data-stu-id="a85a3-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to</span></span> <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a><span data-ttu-id="a85a3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a85a3-110">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="a85a3-111">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a85a3-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="a85a3-112">Использование управляемых графических классов</span><span class="sxs-lookup"><span data-stu-id="a85a3-112">Using Managed Graphics Classes</span></span>](../advanced/using-managed-graphics-classes.md)
- [<span data-ttu-id="a85a3-113">Практическое руководство. Рисование непрозрачных и полупрозрачных линий</span><span class="sxs-lookup"><span data-stu-id="a85a3-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
