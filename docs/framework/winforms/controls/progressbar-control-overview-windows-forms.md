---
title: "Общие сведения об элементе управления ProgressBar (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ProgressBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления хода выполнения, сведения об элементах управления хода выполнения"
  - "ProgressBar - элемент управления [Windows Forms], сведения об элементе управления ProgressBar"
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об элементе управления ProgressBar (Windows Forms)
> [!IMPORTANT]
>  Элемент управления <xref:System.Windows.Forms.ToolStripProgressBar> заменяет элемент управления <xref:System.Windows.Forms.ProgressBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ProgressBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Элемент управления форм Windows Forms <xref:System.Windows.Forms.ProgressBar> показывает, на какой стадии находится выполняемый процесс, что выражается в соответствующем числе прямоугольников, расположенных на горизонтальной шкале.  Завершение процесса характеризуется заполненной шкалой.  Индикаторы выполнения обычно используются, чтобы показать пользователю время, оставшееся до завершения процесса, например при загрузке большого файла.  
  
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ProgressBar> может быть ориентирован в форме только горизонтально.  
  
## Ключевые свойства и методы  
 Ключевыми свойствами элемента управления <xref:System.Windows.Forms.ProgressBar> являются <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A>.  Свойства <xref:System.Windows.Forms.ProgressBar.Minimum%2A> и <xref:System.Windows.Forms.ProgressBar.Maximum%2A> задают минимальное и максимальное значения, отображаемые на индикаторе выполнения.  Свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> представляет объем выполненной работы для завершения операции.  Поскольку полоска, отображаемая в этом элементе управления, состоит из блоков, значение, отображаемое в <xref:System.Windows.Forms.ProgressBar>, представляет только приблизительное текущее значение свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>.  Свойство <xref:System.Windows.Forms.ProgressBar.Value%2A> определяет момент отображения следующего блока исходя из размера <xref:System.Windows.Forms.ProgressBar>.  
  
 Наиболее распространенным способом обновления текущего значения выполнения является запись кода, задающего свойство <xref:System.Windows.Forms.ProgressBar.Value%2A>.  Например, при загрузке большого файла можно задать в качестве максимального значения размер файла в килобайтах.  Так, если для свойства <xref:System.Windows.Forms.ProgressBar.Maximum%2A> задано значение 100, для свойства <xref:System.Windows.Forms.ProgressBar.Minimum%2A> — значение 10, а для свойства <xref:System.Windows.Forms.ProgressBar.Value%2A> — значение 50, на шкале отобразятся 5 прямоугольников.  Это составляет половину числа, которое может быть отображено.  
  
 Однако помимо непосредственного задания свойства <xref:System.Windows.Forms.ProgressBar.Value%2A> существуют другие способы изменить значение, отображаемое в элементе управления <xref:System.Windows.Forms.ProgressBar>.  Можно использовать свойство <xref:System.Windows.Forms.ProgressBar.Step%2A> для указания значения шага изменения свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>.  При этом значение будет изменяться при вызове метода <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>.  Для изменения значения приращения можно использовать метод <xref:System.Windows.Forms.ProgressBar.Increment%2A> и задать значение, которое будет использовать для приращения свойства <xref:System.Windows.Forms.ProgressBar.Value%2A>.  
  
 Другим элементом управления для графического представления пользователю сведений о текущем действии является элемент управления <xref:System.Windows.Forms.StatusBar>.  
  
> [!IMPORTANT]
>  Элементы управления <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> заменяют элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> и расширяют их функциональные возможности; однако при необходимости элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> можно сохранить для обратной совместимости и использования в будущем.  
  
## См. также  
 <xref:System.Windows.Forms.ProgressBar>   
 [Элемент управления ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)