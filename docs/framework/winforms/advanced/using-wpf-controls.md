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
ms.openlocfilehash: 5ea92b24a2ca30c0ad137d83c8f521a952ad0c6b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658490"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Использование элементов управления WPF в Windows Forms приложениях

Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях на основе Windows Forms. Хотя это две различные технологии представления, они беспрепятственно взаимодействуют.

Конструктор Windows Forms в Visual Studio предоставляет среду визуального проектирования для размещения элементов управления Windows Presentation Foundation. Элемент управления WPF размещается на специальном элементе управления Windows Forms с <xref:System.Windows.Forms.Integration.ElementHost>именем. Этот элемент управления позволяет элементу управления WPF участвовать в макете формы и принимать сообщения клавиатуры и мыши. Во время разработки можно разместить <xref:System.Windows.Forms.Integration.ElementHost> элемент управления так же, как любой Windows Forms управления.

Можно также использовать элементы управления Windows Forms в приложениях на основе WPF. Дополнительные сведения см. [в разделе Разработка XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

## <a name="see-also"></a>См. также

- [Взаимодействие WPF и Windows Forms](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
