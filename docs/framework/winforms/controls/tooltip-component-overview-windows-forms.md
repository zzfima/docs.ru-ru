---
title: Общие сведения об элементе управления ToolTip
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741902"
---
# <a name="tooltip-component-overview-windows-forms"></a>Общие сведения о компоненте ToolTip (Windows Forms)
Компонент <xref:System.Windows.Forms.ToolTip> в Windows Forms отображает текст при наведении указателя мыши на элементы управления. Компонент ToolTip можно связать с любым элементом управления. Пример использования этого компонента: для экономии пространства в форме можно отобразить маленький значок на кнопке и использовать подсказку для объяснения функции кнопки.  
  
## <a name="working-with-the-tooltip-component"></a>Работа с компонентом ToolTip  
 Компонент <xref:System.Windows.Forms.ToolTip> предоставляет свойство `ToolTip` для нескольких элементов управления в форме Windows или другом контейнере. Например, если поместить один компонент <xref:System.Windows.Forms.ToolTip> в форму, можно отобразить "введите здесь имя здесь" для элемента управления <xref:System.Windows.Forms.TextBox> и "щелкните здесь, чтобы сохранить изменения" для элемента управления <xref:System.Windows.Forms.Button>.  
  
 Ключевыми методами <xref:System.Windows.Forms.ToolTip> компонента являются <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> и <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. Можно использовать метод <xref:System.Windows.Forms.ToolTip.SetToolTip%2A>, чтобы задать всплывающие подсказки, отображаемые для элементов управления. Дополнительные сведения см. в разделе [как задать подсказки для элементов управления в форме Windows во время разработки](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Ключевыми свойствами являются <xref:System.Windows.Forms.ToolTip.Active%2A>, которые должны быть установлены в `true` для отображения всплывающей подсказки, и <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, которое задает продолжительность отображения строки подсказки, время, в течение которого пользователь должен указывать на элемент управления для отображения всплывающей подсказки, а также время, затрачиваемое на отображение последующих окон всплывающей подсказки. Дополнительные сведения см. в разделе [как изменить задержку Windows Forms компонента ToolTip](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolTip>
- [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
