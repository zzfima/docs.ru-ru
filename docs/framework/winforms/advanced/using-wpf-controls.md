---
title: Использование элементов управления WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460693"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Использование элементов управления WPF в Windows Forms приложениях

Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях на основе Windows Forms. Хотя это две различные технологии представления, они беспрепятственно взаимодействуют.

Конструктор Windows Forms в Visual Studio предоставляет среду визуального проектирования для размещения элементов управления Windows Presentation Foundation. Элемент управления WPF размещается на специальном элементе управления Windows Forms с именем <xref:System.Windows.Forms.Integration.ElementHost>. Этот элемент управления позволяет элементу управления WPF участвовать в макете формы и принимать сообщения клавиатуры и мыши. Во время разработки можно упорядочивать элемент управления <xref:System.Windows.Forms.Integration.ElementHost> так же, как любой Windows Formsный контроль.

Можно также использовать элементы управления Windows Forms в приложениях на основе WPF. Дополнительные сведения см. [в разделе Разработка XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>См. также

- [Взаимодействие WPF и Windows Forms](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
