---
title: Отображение азиатских символов с помощью свойства ImeMode
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: d3733f642d4218c851040582ee5637b5486a7804
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208632"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Отображение азиатских символов с помощью свойства ImeMode
<xref:System.Windows.Forms.Control.ImeMode%2A> Свойство используется форм и элементов управления для принудительного определенный режим редактора метода ввода (IME). Редактор метода ввода — это необходимый компонент для написания сценариев на китайском, японском и корейском языках, так как количество символов в этих системах письменности превышает возможности кодирования обычной клавиатуры. Например, в определенном текстовом поле можно разрешить только символы ASCII. В этом случае можно задать <xref:System.Windows.Forms.Control.ImeMode%2A> свойства <xref:System.Windows.Forms.ImeMode> и пользователи только смогут ввести знаки ASCII данное текстовое поле. Значение по умолчанию <xref:System.Windows.Forms.Control.ImeMode%2A> свойство <xref:System.Windows.Forms.ImeMode>, поэтому если задать свойство для формы, все элементы управления в форме будут наследовать эту настройку. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.Control.ImeMode%2A> ) и <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>См. также

[Глобализация приложений Windows Forms](globalizing-windows-forms.md)
