---
title: "Общие сведения об элементе управления ProgressBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c5ca5fd908124b0f38643c7b2833ba591be3b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-control-overview-windows-forms"></a>Общие сведения об элементе управления ProgressBar (Windows Forms)
> [!IMPORTANT]
>  Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Windows Forms <xref:System.Windows.Forms.ProgressBar> элемент управления показывает ход выполнения процесса, выражается в соответствующем числе прямоугольников, расположенных на горизонтальной полосе. После завершения процесса заполняется строке. Индикаторы выполнения обычно используются для предоставления пользователю понять, как long для дождитесь завершения; Например, при большой файл загрузке.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ProgressBar> Управления только может быть имеет горизонтальную ориентацию в форме.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Ключевые свойства <xref:System.Windows.Forms.ProgressBar> управления <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, и <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. <xref:System.Windows.Forms.ProgressBar.Minimum%2A> И <xref:System.Windows.Forms.ProgressBar.Maximum%2A> свойства задать максимальное и минимальное значения, можно отобразить индикатор выполнения. <xref:System.Windows.Forms.ProgressBar.Value%2A> Свойство представляет ход выполнения, выполненный по выполнению операции. Так как строки, отображаемой в элементе управления состоит из блоков, значение, отображаемое <xref:System.Windows.Forms.ProgressBar> управления лишь приблизительно <xref:System.Windows.Forms.ProgressBar.Value%2A> текущее значение свойства. В зависимости от размера <xref:System.Windows.Forms.ProgressBar> управления <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство определяет время отображения следующего блока.  
  
 Наиболее распространенным способом обновления текущего значения хода выполнения заключается в написании кода, чтобы задать <xref:System.Windows.Forms.ProgressBar.Value%2A> свойства. В примере загрузка больших файлов может присвоить максимальный размер файла в килобайтах. Например если <xref:System.Windows.Forms.ProgressBar.Maximum%2A> задано значение 100, <xref:System.Windows.Forms.ProgressBar.Minimum%2A> задано значение 10 и <xref:System.Windows.Forms.ProgressBar.Value%2A> задано значение 50, отображаются прямоугольники 5. Это половины номер, который может быть отображен.  
  
 Однако существуют другие способы для изменения значения, отображаемого в <xref:System.Windows.Forms.ProgressBar> управления, кроме параметра <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство напрямую. <xref:System.Windows.Forms.ProgressBar.Step%2A> Свойство может использоваться для указания значения для увеличения <xref:System.Windows.Forms.ProgressBar.Value%2A> свойства. После этого вызова <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> метод приводит к увеличению значения. Для изменения значения приращения, можно использовать <xref:System.Windows.Forms.ProgressBar.Increment%2A> метод и укажите значения, которое увеличивается <xref:System.Windows.Forms.ProgressBar.Value%2A> свойство.  
  
 Является другим элементом управления для графического представления пользователю сведений о текущем действии <xref:System.Windows.Forms.StatusBar> элемента управления.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> заменить элементы управления и добавить функциональные возможности в <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления можно сохранить для обратной совместимости и использования в будущем, если вы Выберите этот параметр.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ProgressBar>  
 [Элемент управления ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
