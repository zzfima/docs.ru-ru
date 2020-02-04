---
title: Общие сведения об элементе управления ProgressBar
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741276"
---
# <a name="progressbar-control-overview-windows-forms"></a>Общие сведения об элементе управления ProgressBar (Windows Forms)
> [!IMPORTANT]
> Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.ProgressBar> показывает ход выполнения процесса, отображая соответствующее количество прямоугольников, расположенных на горизонтальной полосе. После завершения процесса Панель заполняется. Индикаторы выполнения обычно используются, чтобы дать пользователю представление о том, как долго ожидать завершения процесса. Например, при загрузке большого файла.  
  
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ProgressBar> может быть ориентирован на форму только горизонтально.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Ключевыми свойствами элемента управления <xref:System.Windows.Forms.ProgressBar> являются <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>и <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Свойства <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> задают максимальное и минимальное значения, которые может отображать индикатор выполнения. Свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> представляет ход выполнения операции. Так как панель, отображаемая в элементе управления, состоит из блоков, значение, отображаемое элементом управления <xref:System.Windows.Forms.ProgressBar>, только приближено к текущему значению свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>. В зависимости от размера элемента управления <xref:System.Windows.Forms.ProgressBar> свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> определяет, когда следует отображать следующий блок.  
  
 Наиболее распространенным способом обновления текущего значения хода выполнения является написание кода для установки свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>. В примере загрузки большого файла можно задать максимальный размер файла в килобайтах. Например, если свойство <xref:System.Windows.Forms.ProgressBar.Maximum%2A> имеет значение 100, свойство <xref:System.Windows.Forms.ProgressBar.Minimum%2A> имеет значение 10, а свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> — 50, будут отображены 5 прямоугольников. Это половина числа, которое может быть отображено.  
  
 Однако существуют и другие способы изменения значения, отображаемого элементом управления <xref:System.Windows.Forms.ProgressBar>, помимо непосредственного задания свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>. Свойство <xref:System.Windows.Forms.ProgressBar.Step%2A> можно использовать для задания значения, увеличивающего свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> by. Затем вызов метода <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> увеличит значение. Чтобы изменить значение приращения, можно использовать метод <xref:System.Windows.Forms.ProgressBar.Increment%2A> и указать значение, с которым нужно увеличить свойство <xref:System.Windows.Forms.ProgressBar.Value%2A>.  
  
 Другой элемент управления, графически уведомляющий пользователя о текущем действии, — это элемент управления <xref:System.Windows.Forms.StatusBar>.  
  
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и добавляют функции в элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel>. Однако элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> сохраняются как для обратной совместимости, так и для будущего использования, если вы решили.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ProgressBar>
- [Элемент управления ProgressBar](progressbar-control-windows-forms.md)
