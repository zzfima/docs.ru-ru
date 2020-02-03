---
title: Изменение задержки компонента ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746592"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms
Для компонента Windows Forms <xref:System.Windows.Forms.ToolTip> можно задать несколько значений задержки. Единицей измерения для всех этих свойств является миллисекунда. Свойство <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> определяет, как долго пользователь должен указывать на соответствующий элемент управления для отображения строки подсказки. Свойство <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> задает число миллисекунд, необходимое для отображения последующих строк подсказки при перемещении мыши из одного связанного элемента управления ToolTip в другой. Свойство <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> определяет продолжительность отображения строки подсказки. Эти значения можно задать по отдельности или задав значение свойства <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>. другие свойства задержки задаются на основе значения, присвоенного свойству <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>. Например, если для <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> задано значение N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> имеет значение N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> устанавливается равным значению <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, деленному на 5 (или N/5), а <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> устанавливается в значение, которое в пять раз превышает значение свойства <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (или менее 5N).  
  
### <a name="to-set-the-delay"></a>Установка задержки  
  
1. Задайте следующие свойства, как показано в этом примере.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления ToolTip](tooltip-component-overview-windows-forms.md)
- [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Компонент ToolTip](tooltip-component-windows-forms.md)
