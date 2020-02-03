---
title: Справочные системы
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: c97a22dbdbdcc0eb282b52e16c4ef40914b1d9e7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742246"
---
# <a name="help-systems-in-windows-forms-applications"></a>Справочные системы в приложениях Windows Forms
Одним из наиболее важных кауртесиес, как разработчик приложений, может быть предоставление пользователям возможности системы компетентного. Именно здесь они будут переключаться, когда они переходят в замешательство или не распознают. Предоставление справочной системы в приложении Windows легко осуществляется с помощью [компонента HelpProvider](../controls/helpprovider-component-windows-forms.md).  
  
## <a name="different-types-of-help"></a>Различные типы справки  
 Компонент <xref:System.Windows.Forms.HelpProvider> Windows Forms позволяет связать HTML-файл справки версии 1.x (CHM-файл, созданный с помощью средства HTML Help Workshop, или HTM-файл) с приложением Windows. Компонент <xref:System.Windows.Forms.HelpProvider> можно использовать для предоставления контекстно-зависимой справки для элементов управления Windows Forms или конкретных элементов управления. Кроме того, компонент <xref:System.Windows.Forms.HelpProvider> может открыть файл справки для конкретных областей, таких как Главная страница оглавления, индекс или функция поиска. Общие сведения о компоненте <xref:System.Windows.Forms.HelpProvider> см. в статье Общие сведения о [компоненте HelpProvider](../controls/helpprovider-component-overview-windows-forms.md). Сведения об использовании компонента <xref:System.Windows.Forms.HelpProvider> для отображения всплывающей справки по Windows Forms см. в разделе [как отобразить всплывающую справку](how-to-display-pop-up-help.md). Сведения об использовании компонента <xref:System.Windows.Forms.ToolTip> для отображения справки, относящейся к конкретному элементу управления, см. в разделе [Справка по управлению с помощью подсказок](control-help-using-tooltips.md).  
  
 Вы можете создать файлы HTML Help 1. x с помощью справки HTML. Дополнительные сведения о HTML-справке см. в подразделах «Справка HTML» или в других разделах «Справка HTML» в MSDN.  
  
## <a name="see-also"></a>См. также раздел

- [Интеграция справки пользователя в формы Windows Forms](integrating-user-help-in-windows-forms.md)
- [Компонент HelpProvider](../controls/helpprovider-component-windows-forms.md)
- [Компонент ToolTip](../controls/tooltip-component-windows-forms.md)
- [Общие сведения о Windows Forms](../windows-forms-overview.md)
- [Windows Forms](../index.md)
