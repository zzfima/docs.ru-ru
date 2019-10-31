---
title: Использование элементов управления WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e05ec7fc503565333a4d05662a4e40d8d1193af
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197461"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Использование элементов управления WPF в Windows Forms приложениях

Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях на основе Windows Forms. Хотя это две различные технологии представления, они беспрепятственно взаимодействуют.

Конструктор Windows Forms в Visual Studio предоставляет среду визуального проектирования для размещения элементов управления Windows Presentation Foundation. Элемент управления WPF размещается на специальном элементе управления Windows Forms с именем <xref:System.Windows.Forms.Integration.ElementHost>. Этот элемент управления позволяет элементу управления WPF участвовать в макете формы и принимать сообщения клавиатуры и мыши. Во время разработки можно упорядочивать элемент управления <xref:System.Windows.Forms.Integration.ElementHost> так же, как любой Windows Formsный контроль.

Можно также использовать элементы управления Windows Forms в приложениях на основе WPF. Дополнительные сведения см. [в разделе Разработка XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>См. также

- [Взаимодействие WPF и Windows Forms](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
