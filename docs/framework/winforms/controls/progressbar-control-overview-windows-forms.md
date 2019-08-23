---
title: Общие сведения об элементе управления ProgressBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 7dd434492cd688527ddbce5aaffa442a0b40a9e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968307"
---
# <a name="progressbar-control-overview-windows-forms"></a>Общие сведения об элементе управления ProgressBar (Windows Forms)
> [!IMPORTANT]
> Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления <xref:System.Windows.Forms.ProgressBar> Windows Forms показывает ход выполнения процесса, отображая соответствующее количество прямоугольников, расположенных на горизонтальной полосе. После завершения процесса Панель заполняется. Индикаторы выполнения обычно используются, чтобы дать пользователю представление о том, как долго ожидать завершения процесса. Например, при загрузке большого файла.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ProgressBar> Элемент управления может быть ориентирован на форму только горизонтально.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Ключевыми свойствами <xref:System.Windows.Forms.ProgressBar> элемента управления являются <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>и <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Свойства <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и<xref:System.Windows.Forms.ProgressBar.Maximum%2A> задают максимальное и минимальное значения, которые может отображать индикатор выполнения. <xref:System.Windows.Forms.ProgressBar.Value%2A> Свойство представляет ход выполнения, выполненный в ходе выполнения операции. Поскольку панель, отображаемая в элементе управления, состоит из блоков, значение, отображаемое <xref:System.Windows.Forms.ProgressBar> элементом управления, лишь приблизительно <xref:System.Windows.Forms.ProgressBar.Value%2A> отражает текущее значение свойства. В зависимости от размера <xref:System.Windows.Forms.ProgressBar> элемента управления свойство определяет, <xref:System.Windows.Forms.ProgressBar.Value%2A> когда следует отображать следующий блок.  
  
 Наиболее распространенным способом обновления текущего значения хода выполнения является написание кода для задания <xref:System.Windows.Forms.ProgressBar.Value%2A> свойства. В примере загрузки большого файла можно задать максимальный размер файла в килобайтах. Например, если <xref:System.Windows.Forms.ProgressBar.Maximum%2A> свойство имеет значение 100 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> , свойство имеет значение 10, а <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство имеет значение 50, то отображаются 5 прямоугольников. Это половина числа, которое может быть отображено.  
  
 Однако существуют и другие способы изменения значения, отображаемого <xref:System.Windows.Forms.ProgressBar> элементом управления, помимо непосредственного <xref:System.Windows.Forms.ProgressBar.Value%2A> задания свойства. Свойство можно использовать для указания значения, которое нужно <xref:System.Windows.Forms.ProgressBar.Value%2A> увеличить для свойства. <xref:System.Windows.Forms.ProgressBar.Step%2A> Затем вызов <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> метода приведет к увеличению значения. Чтобы изменить значение приращения, можно использовать <xref:System.Windows.Forms.ProgressBar.Increment%2A> метод и указать значение, с которым нужно <xref:System.Windows.Forms.ProgressBar.Value%2A> увеличить свойство.  
  
 Другой элемент управления, графически уведомляющий пользователя о текущем действии, — <xref:System.Windows.Forms.StatusBar> это элемент управления.  
  
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> Элементы управления <xref:System.Windows.Forms.ToolStripStatusLabel> и заменяют и добавляют функциональные возможности в элементы управления и, однако, элементы управления и сохраняются для обратной совместимости и использования в будущем, если <xref:System.Windows.Forms.StatusStrip> выбрали.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ProgressBar>
- [Элемент управления ProgressBar](progressbar-control-windows-forms.md)
